[index.html](https://github.com/user-attachments/files/24927845/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Local AI Agents | Privacy-First SME Automation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #1a1a1a;
            color: #e5e5e5;
            scroll-behavior: smooth;
        }
        .gradient-text {
            background: linear-gradient(90deg, #a78bfa, #60a5fa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .chat-container {
            height: 400px;
            scrollbar-width: thin;
            scrollbar-color: #333 #1a1a1a;
        }
        .chat-container::-webkit-scrollbar {
            width: 6px;
        }
        .chat-container::-webkit-scrollbar-thumb {
            background-color: #333;
            border-radius: 10px;
        }
        .typing-dot {
            width: 6px;
            height: 6px;
            background: #a78bfa;
            border-radius: 50%;
            animation: bounce 1.4s infinite ease-in-out;
        }
        .typing-dot:nth-child(2) { animation-delay: 0.2s; }
        .typing-dot:nth-child(3) { animation-delay: 0.4s; }
        @keyframes bounce {
            0%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-6px); }
        }
    </style>
</head>
<body class="antialiased">

    <nav class="flex items-center justify-between px-8 py-6 max-w-7xl mx-auto">
        <div class="text-xl font-bold tracking-tighter flex items-center gap-2">
            <div class="w-8 h-8 bg-indigo-600 rounded-lg flex items-center justify-center">
                <div class="w-4 h-4 bg-white rounded-full"></div>
            </div>
            <span>Local<span class="text-indigo-400">Agent</span></span>
        </div>
        <div class="hidden md:flex gap-8 text-sm font-medium text-gray-400">
            <a href="#features" class="hover:text-white transition">Features</a>
            <a href="#chat" class="hover:text-white transition">Get Started</a>
        </div>
    </nav>

    <header class="max-w-7xl mx-auto px-8 pt-20 pb-12 text-center">
        <h1 class="text-5xl md:text-7xl font-bold tracking-tight leading-tight">
            Automate your SME with <br>
            <span class="gradient-text">Privacy-First AI.</span>
        </h1>
        <p class="mt-6 text-gray-400 text-lg md:text-xl max-w-2xl mx-auto leading-relaxed">
            Deploy powerful Local-First AI agents that live on your hardware. No data leaks, no monthly per-user fees, total control.
        </p>
    </header>

    <section id="chat" class="max-w-4xl mx-auto px-6 py-12">
        <div class="bg-[#242424] border border-white/5 rounded-2xl shadow-2xl overflow-hidden">
            <div class="bg-white/5 px-6 py-4 flex items-center justify-between border-b border-white/5">
                <div class="flex items-center gap-3">
                    <div class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></div>
                    <span class="text-xs uppercase tracking-widest font-semibold text-gray-400">AI Consultation Agent</span>
                </div>
                <button onclick="clearChat()" class="text-xs text-gray-500 hover:text-gray-300 transition">Clear History</button>
            </div>

            <div id="chat-window" class="chat-container overflow-y-auto p-6 space-y-4 flex flex-col">
                <div class="bg-indigo-600/10 text-indigo-200 self-start p-4 rounded-2xl rounded-tl-none max-w-[85%] text-sm">
                    Hello! I'm your local automation strategist. How can I help you reclaim your time today?
                </div>
            </div>

            <div id="loading" class="hidden px-6 py-4 flex gap-2">
                <div class="typing-dot"></div>
                <div class="typing-dot"></div>
                <div class="typing-dot"></div>
            </div>

            <form id="chat-form" class="p-4 bg-white/5 border-t border-white/5 flex gap-2">
                <input 
                    type="text" 
                    id="user-input" 
                    placeholder="Type your question..." 
                    class="flex-1 bg-[#1a1a1a] border border-white/10 rounded-xl px-4 py-3 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 transition"
                    required
                >
                <button type="submit" class="bg-indigo-600 hover:bg-indigo-500 text-white px-6 py-3 rounded-xl transition font-semibold text-sm">
                    Send
                </button>
            </form>
        </div>
        <p class="text-center mt-6 text-xs text-gray-600">
            Encrypted interaction. No data is stored on our servers.
        </p>
    </section>

    <section id="features" class="max-w-7xl mx-auto px-8 py-24 grid md:grid-cols-3 gap-12">
        <div class="space-y-4">
            <h3 class="text-lg font-semibold text-indigo-400">Local-First</h3>
            <p class="text-sm text-gray-400">Run LLMs on your own infrastructure. Your data never leaves your network, ensuring 100% compliance with strict privacy laws.</p>
        </div>
        <div class="space-y-4">
            <h3 class="text-lg font-semibold text-indigo-400">Zero Subscriptions</h3>
            <p class="text-sm text-gray-400">Forget $20/mo per seat. Once deployed, these agents operate at the cost of electricity. Infinite scaling for zero extra cost.</p>
        </div>
        <div class="space-y-4">
            <h3 class="text-lg font-semibold text-indigo-400">SME Optimized</h3>
            <p class="text-sm text-gray-400">Pre-built workflows for customer support, document analysis, and lead qualification tailored for small and medium businesses.</p>
        </div>
    </section>

    <footer class="text-center py-12 border-t border-white/5 text-gray-600 text-sm">
        &copy; 2026 LocalAgent AI. Built for the privacy-conscious enterprise.
    </footer>

    <script>
        /** * CONFIGURATION
         * Replace the URL below with your actual n8n production webhook URL
         */
        const N8N_WEBHOOK_URL = '{{N8N_WEBHOOK_URL}}';

        const chatWindow = document.getElementById('chat-window');
        const chatForm = document.getElementById('chat-form');
        const userInput = document.getElementById('user-input');
        const loadingIndicator = document.getElementById('loading');

        // Initialize chat from LocalStorage
        document.addEventListener('DOMContentLoaded', () => {
            const history = JSON.parse(localStorage.getItem('chat_history')) || [];
            history.forEach(msg => appendMessage(msg.role, msg.text));
            scrollToBottom();
        });

        chatForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            const message = userInput.value.trim();
            if (!message) return;

            // Update UI
            appendMessage('user', message);
            saveToStorage('user', message);
            userInput.value = '';
            showLoading(true);

            try {
                const response = await fetch(N8N_WEBHOOK_URL, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        message: message,
                        timestamp: new Date().toISOString(),
                        session_id: getSessionId()
                    })
                });

                if (!response.ok) throw new Error('Network error');

                const data = await response.json();
                // Assuming n8n returns { "output": "..." } or similar structure
                const botReply = data.output || data.response || "I've received your message. One of our engineers will follow up shortly.";
                
                appendMessage('bot', botReply);
                saveToStorage('bot', botReply);

            } catch (error) {
                console.error(error);
                appendMessage('bot', 'Sorry, I am having trouble connecting to the local server. Please try again later.');
            } finally {
                showLoading(false);
                scrollToBottom();
            }
        });

        function appendMessage(role, text) {
            const msgDiv = document.createElement('div');
            const isUser = role === 'user';
            
            msgDiv.className = isUser 
                ? 'bg-white/10 text-gray-200 self-end p-4 rounded-2xl rounded-tr-none max-w-[85%] text-sm'
                : 'bg-indigo-600/10 text-indigo-200 self-start p-4 rounded-2xl rounded-tl-none max-w-[85%] text-sm';
            
            msgDiv.textContent = text;
            chatWindow.appendChild(msgDiv);
            scrollToBottom();
        }

        function showLoading(show) {
            loadingIndicator.classList.toggle('hidden', !show);
            scrollToBottom();
        }

        function scrollToBottom() {
            chatWindow.scrollTop = chatWindow.scrollHeight;
        }

        function saveToStorage(role, text) {
            const history = JSON.parse(localStorage.getItem('chat_history')) || [];
            history.push({ role, text });
            localStorage.setItem('chat_history', JSON.stringify(history));
        }

        function clearChat() {
            localStorage.removeItem('chat_history');
            location.reload();
        }

        function getSessionId() {
            let sid = localStorage.getItem('chat_session_id');
            if (!sid) {
                sid = 'session_' + Math.random().toString(36).substr(2, 9);
                localStorage.setItem('chat_session_id', sid);
            }
            return sid;
        }
    </script>
</body>
</html>
