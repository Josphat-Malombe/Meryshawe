<script setup>
import { ref, onMounted, onBeforeUnmount, nextTick } from 'vue'
import { GoogleGenerativeAI } from '@google/generative-ai'

const apiKey = ''


let genAI
let model
try {
  genAI = new GoogleGenerativeAI(apiKey)
  model = genAI.getGenerativeModel({ model: 'gemini-1.5-flash' }) 
} catch (error) {
  console.error('Failed to initialize chat:', error)
}

const open = ref(false)
const input = ref('')
const messages = ref([
  {
    from: 'agent',
    text: 'Hello!  I’m Precious School’s virtual assistant. How can I help you today?',
  },
])

const systemPrompt = `
You are "Precious School Assistant", a warm, knowledgeable representative of Precious School.
You help parents, students, and visitors with questions about:
- Admissions and enrollment
- Academic programs
- School mission, vision, and values
- Extracurricular activities and culture
Keep answers short, friendly, and professional. If someone asks unrelated questions, gently guide them back to school-related topics.
The site has a lot of links to most info, so suggest they check there if needed.
`

const toggle = () => {
  open.value = !open.value
  if (open.value) {
    nextTick(() => {
      const el = document.querySelector('.chat-input')
      if (el) el.focus()
    })
  }
}

async function sendMessage(ev) {
  ev?.preventDefault()
  const text = input.value.trim()
  if (!text) return
  messages.value.push({ from: 'user', text })
  input.value = ''

  nextTick(() => {
    const box = document.querySelector('.chat-messages')
    if (box) box.scrollTop = box.scrollHeight
  })

  try {
    const prompt = `${systemPrompt}\n\nUser: ${text}`
    const result = await model.generateContent(prompt)
    const reply = result.response.text()
    messages.value.push({ from: 'agent', text: reply })
  } catch (e) {
    messages.value.push({
      from: 'agent',
      text: 'Sorry, I’m having trouble connecting with the school server right now. Please try again later.',
    })
  }

  nextTick(() => {
    const box = document.querySelector('.chat-messages')
    if (box) box.scrollTop = box.scrollHeight
  })
}

function handleClickOutside(e) {
  const chatRoot = document.querySelector('.chat-agent-root')
  if (!chatRoot.contains(e.target)) open.value = false
}

function handleEsc(e) {
  if (e.key === 'Escape') open.value = false
}

onMounted(() => {
  window.addEventListener('click', handleClickOutside)
  window.addEventListener('keydown', handleEsc)
})

onBeforeUnmount(() => {
  window.removeEventListener('click', handleClickOutside)
  window.removeEventListener('keydown', handleEsc)
})
</script>

<template>
  <div class="chat-agent-root" aria-live="polite">
    <button
      class="chat-fab"
      :aria-expanded="open"
      aria-label="Open chat"
      @click.stop="toggle"
      title="Chat with us"
    >
      <svg width="26" height="26" viewBox="0 0 24 24" fill="none">
    <path d="M12 2C7 2 3 6 3 11v4c0 3 2 5 5 5h1v2a1 1 0 0 0 1.6.8l3.4-2.8h2c3 0 5-2 5-5v-4c0-5-4-9-9-9z"
          stroke="white" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="9" cy="11" r="1" fill="white"/>
    <circle cx="15" cy="11" r="1" fill="white"/>
  </svg>
    </button>

    <div class="chat-window" v-if="open" role="dialog" aria-label="Chat window" @click.stop>
      <header class="chat-header">
        <div>
          <strong>Precious School</strong>
          <div class="chat-sub">Virtual Assistant</div>
        </div>
        <button class="chat-close" aria-label="Close chat" @click="open = false">✕</button>
      </header>

      <main class="chat-messages" role="log" aria-live="polite">
        <div v-for="(m, i) in messages" :key="i" :class="['msg', m.from]">
          <div class="msg-text">{{ m.text }}</div>
        </div>
      </main>

      <form class="chat-input-row" @submit="sendMessage">
        <input
          class="chat-input"
          v-model="input"
          placeholder="Type your message..."
          aria-label="Type your message"
        />
        <button type="submit" class="chat-send" aria-label="Send message">Send</button>
      </form>
    </div>
  </div>
</template>

<style scoped>
.chat-agent-root {
  position: fixed;
  right: 20px;
  bottom: 20px;
  z-index: 9999;
  font-family:
    Inter,
    system-ui,
    -apple-system,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial;
}

.chat-fab {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  border: none;
  background: linear-gradient(180deg, #8b0000, #6d0000);
  color: #fff;
  display: inline-grid;
  place-items: center;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.25);
  cursor: pointer;
}

.chat-window {
  width: 340px;
  max-width: calc(100vw - 40px);
  height: 420px;
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 14px 40px rgba(20, 20, 20, 0.25);
  margin-bottom: 12px;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  transform-origin: bottom right;
  animation: pop 160ms ease-out;
}

@keyframes pop {
  from {
    transform: scale(0.96);
    opacity: 0;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}

.chat-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 14px;
  border-bottom: 1px solid #eee;
  background: linear-gradient(90deg, #6d0000, #8b1f1f);
  color: #fff;
}
.chat-header .chat-sub {
  font-size: 12px;
  opacity: 0.9;
}

.chat-close {
  background: transparent;
  border: none;
  color: #fff;
  font-size: 16px;
  cursor: pointer;
}

.chat-messages {
  flex: 1;
  padding: 12px;
  overflow-y: auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
  background: #fafafa;
}

.msg {
  display: inline-block;
  max-width: 78%;
  padding: 8px 12px;
  border-radius: 12px;
  line-height: 1.3;
}
.msg.agent {
  background: #fff;
  color: #222;
  margin-right: auto;
  align-self: flex-start;
  border: 1px solid #eee;
}
.msg.user {
  background: linear-gradient(90deg, #8b0000, #6d0000);
  color: #fff;
  align-self: flex-end;
}

.chat-input-row {
  display: flex;
  gap: 8px;
  padding: 10px;
  border-top: 1px solid #eee;
  background: #fff;
}
.chat-input {
  flex: 1;
  padding: 8px 10px;
  border: 1px solid #ddd;
  border-radius: 8px;
  font-size: 14px;
  outline: none;
}
.chat-send {
  background: #6d0000;
  color: white;
  border: none;
  padding: 8px 12px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
}

@media (max-width: 460px) {
  .chat-window {
    width: calc(100vw - 24px);
    right: 12px;
    bottom: 12px;
    height: 56vh;
  }
  .chat-agent-root {
    right: 12px;
    bottom: 12px;
  }
}
</style>
