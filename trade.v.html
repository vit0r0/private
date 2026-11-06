<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CryptoPulse - Live Market Dashboard</title>
    <!-- Tailwind CSS for rapid UI development -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        darkbg: '#0B0F19',
                        cardbg: '#111827',
                        bordercolor: '#1F2937'
                    },
                    animation: {
                        'spin-slow': 'spin 2s linear infinite',
                        'pulse-fast': 'pulse 1s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    }
                }
            }
        }
    </script>
    <!-- Inter Font -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Phosphor Icons for elegant UI symbols -->
    <script src="https://unpkg.com/@phosphor-icons/web"></script>
    
    <style>
        /* Custom Scrollbar for a polished look */
        ::-webkit-scrollbar { width: 6px; height: 6px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: #374151; border-radius: 10px; }
        ::-webkit-scrollbar-thumb:hover { background: #4B5563; }

        /* Glassmorphism utility */
        .glass-header {
            background: rgba(17, 24, 39, 0.8);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid #1F2937;
        }

        /* Row Entry Animation */
        .row-enter {
            animation: slideIn 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
            opacity: 0;
            transform: translateY(10px);
        }

        @keyframes slideIn {
            to { opacity: 1; transform: translateY(0); }
        }

        /* Green/Red flash animation on update */
        .flash-up { animation: flashGreen 1s ease-out; }
        .flash-down { animation: flashRed 1s ease-out; }

        @keyframes flashGreen {
            0% { background-color: rgba(16, 185, 129, 0.2); }
            100% { background-color: transparent; }
        }
        @keyframes flashRed {
            0% { background-color: rgba(239, 68, 68, 0.2); }
            100% { background-color: transparent; }
        }
    </style>
</head>
<body class="bg-darkbg text-slate-300 font-sans min-h-screen overflow-x-hidden">

    <!-- Sticky Header -->
    <header class="glass-header sticky top-0 z-50 w-full">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo & Title -->
                <div class="flex items-center gap-3">
                    <div class="bg-blue-600 p-2 rounded-lg text-white">
                        <i class="ph ph-chart-line-up text-xl"></i>
                    </div>
                    <h1 class="text-xl font-bold text-white tracking-tight">Crypto<span class="text-blue-500">Pulse</span></h1>
                </div>

                <!-- Controls & Status -->
                <div class="flex items-center gap-4 sm:gap-6">
                    <div class="hidden sm:flex items-center gap-2 text-sm text-slate-400">
                        <span id="status-indicator" class="relative flex h-2.5 w-2.5">
                            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-400 opacity-75"></span>
                            <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-green-500"></span>
                        </span>
                        <span id="status-text">Live updates</span>
                    </div>

                    <div class="flex items-center gap-3 bg-slate-800/50 rounded-full px-4 py-1.5 border border-bordercolor">
                        <span class="text-sm font-medium text-slate-300" id="countdown-timer">60s</span>
                        <button id="refresh-btn" class="text-slate-400 hover:text-white transition-colors p-1 rounded-full hover:bg-slate-700 outline-none" title="Refresh Now">
                            <i class="ph ph-arrows-clockwise text-lg"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        
        <!-- Stats Overview -->
        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-8" id="market-overview">
            <div class="bg-cardbg border border-bordercolor rounded-xl p-5 flex flex-col justify-center">
                <span class="text-sm font-medium text-slate-400 mb-1">Global Market Cap</span>
                <div class="text-2xl font-bold text-white flex items-baseline gap-2">
                    <span id="global-mcap">Loading...</span>
                </div>
            </div>
            <div class="bg-cardbg border border-bordercolor rounded-xl p-5 flex flex-col justify-center">
                <span class="text-sm font-medium text-slate-400 mb-1">24h Volume</span>
                <div class="text-2xl font-bold text-white">
                    <span id="global-vol">Loading...</span>
                </div>
            </div>
            <div class="bg-cardbg border border-bordercolor rounded-xl p-5 flex flex-col justify-center">
                <span class="text-sm font-medium text-slate-400 mb-1">BTC Dominance</span>
                <div class="text-2xl font-bold text-white">
                    <span id="btc-dom">Loading...</span>
                </div>
            </div>
        </div>

        <!-- Table Container -->
        <div class="bg-cardbg border border-bordercolor rounded-xl shadow-2xl overflow-hidden relative">
            
            <!-- Loading Overlay -->
            <div id="loading-overlay" class="absolute inset-0 bg-cardbg/80 backdrop-blur-sm z-10 flex flex-col items-center justify-center transition-opacity duration-300">
                <i class="ph ph-spinner-gap text-4xl text-blue-500 animate-spin mb-4"></i>
                <p class="text-slate-300 font-medium">Fetching market data...</p>
            </div>

            <!-- Error Banner -->
            <div id="error-banner" class="hidden bg-red-500/10 border-b border-red-500/20 p-3 text-center text-sm text-red-400">
                <i class="ph ph-warning-circle align-middle mr-1 text-lg"></i>
                <span id="error-text">Network error. Showing cached/fallback data.</span>
            </div>

            <div class="overflow-x-auto">
                <table class="w-full text-left border-collapse whitespace-nowrap">
                    <thead>
                        <tr class="text-xs uppercase tracking-wider text-slate-400 border-b border-bordercolor bg-slate-800/30">
                            <th class="px-6 py-4 font-semibold w-12 text-center">#</th>
                            <th class="px-6 py-4 font-semibold">Asset</th>
                            <th class="px-6 py-4 font-semibold text-right">Price (USD)</th>
                            <th class="px-6 py-4 font-semibold text-right">24h Change</th>
                            <th class="px-6 py-4 font-semibold text-right hidden md:table-cell">Market Cap</th>
                            <th class="px-6 py-4 font-semibold text-right hidden lg:table-cell">Volume (24h)</th>
                        </tr>
                    </thead>
                    <tbody id="crypto-table-body" class="divide-y divide-bordercolor">
                        <!-- Rows injected via JS -->
                    </tbody>
                </table>
            </div>
        </div>
        
        <div class="mt-6 flex justify-between items-center text-xs text-slate-500">
            <p>Data provided by <a href="https://www.coingecko.com/" target="_blank" class="text-blue-400 hover:underline">CoinGecko</a> API.</p>
            <p id="last-updated-text">Last updated: --</p>
        </div>
    </main>

    <script>
        // --- Configuration & State ---
        const API_URL = 'https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=30&page=1&sparkline=false';
        const REFRESH_INTERVAL = 60; // seconds
        
        let state = {
            data: [],
            previousData: {}, // Map of id -> previous price for flash animations
            countdown: REFRESH_INTERVAL,
            timerInterval: null,
            isFetching: false
        };

        // --- DOM Elements ---
        const tableBody = document.getElementById('crypto-table-body');
        const loadingOverlay = document.getElementById('loading-overlay');
        const countdownEl = document.getElementById('countdown-timer');
        const refreshBtn = document.getElementById('refresh-btn');
        const errorBanner = document.getElementById('error-banner');
        const errorText = document.getElementById('error-text');
        const lastUpdatedText = document.getElementById('last-updated-text');
        const refreshIcon = refreshBtn.querySelector('i');
        const statusIndicator = document.getElementById('status-indicator').querySelector('.animate-ping');

        // --- Formatters ---
        const formatCurrency = (val) => {
            if (val === null || val === undefined) return 'N/A';
            return new Intl.NumberFormat('en-US', {
                style: 'currency',
                currency: 'USD',
                minimumFractionDigits: val < 1 ? 4 : 2,
                maximumFractionDigits: val < 1 ? 6 : 2
            }).format(val);
        };

        const formatCompactCurrency = (val) => {
            if (val === null || val === undefined) return 'N/A';
            return new Intl.NumberFormat('en-US', {
                style: 'currency',
                currency: 'USD',
                notation: "compact",
                maximumFractionDigits: 2
            }).format(val);
        };

        const formatPercent = (val) => {
            if (val === null || val === undefined) return '0.00%';
            const sign = val > 0 ? '+' : '';
            return `${sign}${val.toFixed(2)}%`;
        };

        // --- API & Data Handling ---
        async function fetchCryptoData() {
            if (state.isFetching) return;
            state.isFetching = true;
            refreshIcon.classList.add('animate-spin');
            
            try {
                const response = await fetch(API_URL);
                if (!response.ok) {
                    throw new Error(response.status === 429 ? 'Rate limit exceeded' : 'Network response was not ok');
                }
                const data = await response.json();
                
                // Store previous data to calculate flash direction
                state.data.forEach(coin => {
                    state.previousData[coin.id] = coin.current_price;
                });
                
                state.data = data;
                hideError();
                renderTable();
                updateOverviewStats(data);
                
            } catch (error) {
                console.warn('API Fetch failed, using fallback.', error);
                showError(`API Error: ${error.message}. Showing mock data.`);
                
                // Generate mock data if API fails to keep demo alive
                if (state.data.length === 0) {
                    state.data = generateMockData();
                } else {
                    // Simulate price fluctuation in mock mode
                    state.data = state.data.map(coin => ({
                        ...coin,
                        current_price: coin.current_price * (1 + (Math.random() - 0.5) * 0.01),
                        price_change_percentage_24h: coin.price_change_percentage_24h + (Math.random() - 0.5)
                    }));
                }
                renderTable();
                updateOverviewStats(state.data);
            } finally {
                state.isFetching = false;
                refreshIcon.classList.remove('animate-spin');
                loadingOverlay.classList.add('opacity-0', 'pointer-events-none');
                updateLastUpdatedTime();
                resetCountdown();
            }
        }

        // --- UI Rendering ---
        function renderTable() {
            tableBody.innerHTML = '';
            
            state.data.forEach((coin, index) => {
                const prevPrice = state.previousData[coin.id];
                const currentPrice = coin.current_price;
                
                // Determine animation class if price changed
                let flashClass = '';
                if (prevPrice !== undefined && prevPrice !== currentPrice) {
                    flashClass = currentPrice > prevPrice ? 'flash-up' : 'flash-down';
                }

                const isPositive = coin.price_change_percentage_24h >= 0;
                const changeColorClass = isPositive ? 'text-green-400' : 'text-red-400';
                const changeIcon = isPositive ? 'ph-trend-up' : 'ph-trend-down';
                const delay = index * 0.03; // Staggered entry animation

                const tr = document.createElement('tr');
                tr.className = `hover:bg-slate-800/50 transition-colors duration-200 row-enter ${flashClass}`;
                tr.style.animationDelay = `${delay}s`;
                
                tr.innerHTML = `
                    <td class="px-6 py-4 text-sm text-slate-500 text-center font-medium">${coin.market_cap_rank || index + 1}</td>
                    <td class="px-6 py-4">
                        <div class="flex items-center gap-3">
                            <img src="${coin.image}" alt="${coin.name} logo" class="w-8 h-8 rounded-full bg-slate-800 object-cover" onerror="this.src='https://placehold.co/32x32/1E293B/FFF?text=${coin.symbol.charAt(0).toUpperCase()}'">
                            <div class="flex flex-col">
                                <span class="font-bold text-slate-200 leading-tight">${coin.name}</span>
                                <span class="text-xs text-slate-500 uppercase font-medium">${coin.symbol}</span>
                            </div>
                        </div>
                    </td>
                    <td class="px-6 py-4 text-right font-medium text-slate-200">
                        ${formatCurrency(coin.current_price)}
                    </td>
                    <td class="px-6 py-4 text-right">
                        <div class="flex items-center justify-end gap-1 ${changeColorClass} font-medium bg-opacity-10 py-1 px-2 rounded ml-auto w-fit">
                            <i class="ph ${changeIcon}"></i>
                            ${formatPercent(coin.price_change_percentage_24h)}
                        </div>
                    </td>
                    <td class="px-6 py-4 text-right text-slate-400 hidden md:table-cell font-medium">
                        ${formatCompactCurrency(coin.market_cap)}
                    </td>
                    <td class="px-6 py-4 text-right text-slate-400 hidden lg:table-cell font-medium">
                        ${formatCompactCurrency(coin.total_volume)}
                    </td>
                `;
                tableBody.appendChild(tr);
            });
        }

        function updateOverviewStats(data) {
            if (!data || data.length === 0) return;
            
            // Calculate pseudo global stats from top 30
            const totalMcap = data.reduce((sum, coin) => sum + (coin.market_cap || 0), 0);
            const totalVol = data.reduce((sum, coin) => sum + (coin.total_volume || 0), 0);
            
            let btcDom = "N/A";
            const btc = data.find(c => c.symbol.toLowerCase() === 'btc');
            if (btc && totalMcap > 0) {
                btcDom = ((btc.market_cap / totalMcap) * 100).toFixed(1) + '%';
            }

            document.getElementById('global-mcap').textContent = formatCompactCurrency(totalMcap);
            document.getElementById('global-vol').textContent = formatCompactCurrency(totalVol);
            document.getElementById('btc-dom').textContent = btcDom;
        }

        function updateLastUpdatedTime() {
            const now = new Date();
            const timeString = now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' });
            lastUpdatedText.textContent = `Last updated: ${timeString}`;
        }

        function showError(msg) {
            errorText.textContent = msg;
            errorBanner.classList.remove('hidden');
            statusIndicator.classList.remove('bg-green-400');
            statusIndicator.classList.add('bg-yellow-400');
        }

        function hideError() {
            errorBanner.classList.add('hidden');
            statusIndicator.classList.remove('bg-yellow-400');
            statusIndicator.classList.add('bg-green-400');
        }

        // --- Timer Logic ---
        function startTimer() {
            if (state.timerInterval) clearInterval(state.timerInterval);
            
            state.timerInterval = setInterval(() => {
                state.countdown--;
                countdownEl.textContent = `${state.countdown}s`;
                
                if (state.countdown <= 0) {
                    fetchCryptoData();
                }
            }, 1000);
        }

        function resetCountdown() {
            state.countdown = REFRESH_INTERVAL;
            countdownEl.textContent = `${state.countdown}s`;
        }

        // --- Mock Data Generator (Fallback for rate limits) ---
        function generateMockData() {
            const symbols = ['BTC', 'ETH', 'USDT', 'BNB', 'SOL', 'USDC', 'XRP', 'ADA', 'AVAX', 'DOGE', 'TRX', 'DOT', 'LINK', 'MATIC', 'TON'];
            const names = ['Bitcoin', 'Ethereum', 'Tether', 'BNB', 'Solana', 'USDC', 'XRP', 'Cardano', 'Avalanche', 'Dogecoin', 'TRON', 'Polkadot', 'Chainlink', 'Polygon', 'Toncoin'];
            const bases = [64000, 3100, 1, 580, 140, 1, 0.6, 0.5, 45, 0.15, 0.12, 8, 18, 0.9, 6];
            
            return symbols.map((sym, i) => {
                const basePrice = bases[i];
                // Random variation for realism
                const price = basePrice * (1 + (Math.random() - 0.5) * 0.05);
                const change = (Math.random() - 0.5) * 10;
                
                return {
                    id: names[i].toLowerCase(),
                    symbol: sym.toLowerCase(),
                    name: names[i],
                    image: `https://assets.coingecko.com/coins/images/1/large/bitcoin.png`, // Generic fallback or use specific ones if needed, placeholder handles 404s
                    current_price: price,
                    market_cap: price * (1000000000 / (i + 1)), // Fake market cap
                    market_cap_rank: i + 1,
                    total_volume: price * 50000000, // Fake volume
                    price_change_percentage_24h: change
                };
            });
        }

        // --- Event Listeners & Initialization ---
        refreshBtn.addEventListener('click', () => {
            fetchCryptoData();
        });

        // Initial Load
        window.addEventListener('DOMContentLoaded', () => {
            fetchCryptoData();
            startTimer();
        });

    </script>
</body>
</html>
