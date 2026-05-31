Action: file_editor create /app/cps-counter.html --file-text "<!DOCTYPE html>

<html lang=\"en\">  
<head>  
    <meta charset=\"UTF-8\">  
    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">  
    <meta name=\"description\" content=\"Test your clicking speed with our CPS Counter. Measure your Clicks Per Second with accurate timing and track your personal best scores.\">  
    <meta name=\"keywords\" content=\"CPS counter, clicks per second, click speed test, clicking game, mouse speed test\">  
    <meta name=\"author\" content=\"CPS Counter\">  
    <meta property=\"og:title\" content=\"CPS Counter - Test Your Clicking Speed\">  
    <meta property=\"og:description\" content=\"Measure your clicks per second and improve your clicking speed with our professional CPS counter tool.\">  
    <meta property=\"og:type\" content=\"website\">  
    <meta name=\"twitter:card\" content=\"summary_large_image\">  
    <meta name=\"twitter:title\" content=\"CPS Counter - Test Your Clicking Speed\">  
    <meta name=\"twitter:description\" content=\"Test and improve your clicking speed with accurate CPS measurement.\">  
    <title>CPS Counter - Test Your Clicking Speed | Clicks Per Second</title>  
    <link rel=\"preconnect\" href=\"https://fonts.googleapis.com\">  
    <link rel=\"preconnect\" href=\"https://fonts.gstatic.com\" crossorigin>  
    <link href=\"https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;600;700;800&display=swap\" rel=\"stylesheet\">  
    <style>  
        * {  
            margin: 0;  
            padding: 0;  
            box-sizing: border-box;  
        }  body {  
        font-family: 'Manrope', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;  
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);  
        min-height: 100vh;  
        display: flex;  
        flex-direction: column;  
        align-items: center;  
        justify-content: center;  
        padding: 20px;  
        color: #333;  
        overflow-x: hidden;  
    }  

    .container {  
        width: 100%;  
        max-width: 900px;  
        margin: 0 auto;  
    }  

    .header {  
        text-align: center;  
        margin-bottom: 40px;  
        animation: fadeInDown 0.6s ease-out;  
    }  

    .header h1 {  
        font-size: 3.5rem;  
        font-weight: 800;  
        color: #ffffff;  
        margin-bottom: 12px;  
        text-shadow: 2px 4px 12px rgba(0, 0, 0, 0.2);  
        letter-spacing: -1px;  
    }  

    .header p {  
        font-size: 1.1rem;  
        color: rgba(255, 255, 255, 0.9);  
        font-weight: 500;  
    }  

    .main-card {  
        background: #ffffff;  
        border-radius: 24px;  
        padding: 40px;  
        box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);  
        margin-bottom: 30px;  
        animation: fadeInUp 0.6s ease-out;  
    }  

    .timer-options {  
        display: flex;  
        gap: 12px;  
        justify-content: center;  
        margin-bottom: 30px;  
        flex-wrap: wrap;  
    }  

    .timer-btn {  
        padding: 12px 28px;  
        border: 2px solid #667eea;  
        background: transparent;  
        color: #667eea;  
        border-radius: 50px;  
        font-size: 1rem;  
        font-weight: 600;  
        cursor: pointer;  
        font-family: 'Manrope', sans-serif;  
        transition: all 0.3s ease;  
    }  

    .timer-btn:hover {  
        background: #667eea;  
        color: #ffffff;  
        transform: translateY(-2px);  
        box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);  
    }  

    .timer-btn.active {  
        background: #667eea;  
        color: #ffffff;  
        box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);  
    }  

    .click-area {  
        background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);  
        min-height: 350px;  
        border-radius: 20px;  
        display: flex;  
        flex-direction: column;  
        align-items: center;  
        justify-content: center;  
        cursor: pointer;  
        user-select: none;  
        margin-bottom: 30px;  
        transition: all 0.2s ease;  
        position: relative;  
        overflow: hidden;  
    }  

    .click-area:hover {  
        transform: scale(1.02);  
        box-shadow: 0 12px 40px rgba(245, 87, 108, 0.4);  
    }  

    .click-area:active {  
        transform: scale(0.98);  
    }  

    .click-area.testing {  
        animation: pulse 1s infinite;  
    }  

    .click-area.finished {  
        background: linear-gradient(135deg, #84fab0 0%, #8fd3f4 100%);  
        cursor: default;  
    }  

    .click-area.finished:hover {  
        transform: none;  
    }  

    .click-count {  
        font-size: 6rem;  
        font-weight: 800;  
        color: #ffffff;  
        text-shadow: 3px 3px 12px rgba(0, 0, 0, 0.2);  
        margin-bottom: 10px;  
        line-height: 1;  
    }  

    .click-label {  
        font-size: 1.5rem;  
        color: rgba(255, 255, 255, 0.95);  
        font-weight: 600;  
        margin-bottom: 20px;  
    }  

    .timer-display {  
        font-size: 2rem;  
        color: rgba(255, 255, 255, 0.9);  
        font-weight: 700;  
        background: rgba(0, 0, 0, 0.15);  
        padding: 8px 24px;  
        border-radius: 50px;  
        backdrop-filter: blur(10px);  
    }  

    .instruction-text {  
        font-size: 1.3rem;  
        color: #ffffff;  
        font-weight: 600;  
        text-align: center;  
    }  

    .results {  
        display: grid;  
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));  
        gap: 20px;  
        margin-bottom: 30px;  
    }  

    .result-card {  
        background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);  
        padding: 24px;  
        border-radius: 16px;  
        text-align: center;  
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);  
    }  

    .result-value {  
        font-size: 2.5rem;  
        font-weight: 800;  
        color: #333;  
        margin-bottom: 8px;  
    }  

    .result-label {  
        font-size: 0.95rem;  
        color: #666;  
        font-weight: 600;  
        text-transform: uppercase;  
        letter-spacing: 0.5px;  
    }  

    .reset-btn {  
        width: 100%;  
        padding: 16px;  
        background: #667eea;  
        color: #ffffff;  
        border: none;  
        border-radius: 12px;  
        font-size: 1.1rem;  
        font-weight: 700;  
        cursor: pointer;  
        font-family: 'Manrope', sans-serif;  
        transition: all 0.3s ease;  
        box-shadow: 0 6px 20px rgba(102, 126, 234, 0.3);  
    }  

    .reset-btn:hover {  
        background: #5568d3;  
        transform: translateY(-2px);  
        box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);  
    }  

    .reset-btn:active {  
        transform: translateY(0);  
    }  

    .stats-section {  
        background: #ffffff;  
        border-radius: 24px;  
        padding: 40px;  
        box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);  
        animation: fadeInUp 0.6s ease-out 0.2s both;  
    }  

    .stats-title {  
        font-size: 2rem;  
        font-weight: 800;  
        color: #333;  
        margin-bottom: 24px;  
        text-align: center;  
    }  

    .personal-best {  
        background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);  
        padding: 28px;  
        border-radius: 16px;  
        text-align: center;  
        margin-bottom: 30px;  
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);  
    }  

    .best-score {  
        font-size: 3rem;  
        font-weight: 800;  
        color: #333;  
        margin-bottom: 8px;  
    }  

    .best-label {  
        font-size: 1.1rem;  
        color: #666;  
        font-weight: 600;  
    }  

    .history-list {  
        max-height: 300px;  
        overflow-y: auto;  
    }  

    .history-item {  
        background: #f8f9fa;  
        padding: 16px 20px;  
        border-radius: 12px;  
        margin-bottom: 12px;  
        display: flex;  
        justify-content: space-between;  
        align-items: center;  
        transition: all 0.2s ease;  
    }  

    .history-item:hover {  
        background: #e9ecef;  
        transform: translateX(4px);  
    }  

    .history-score {  
        font-size: 1.5rem;  
        font-weight: 700;  
        color: #667eea;  
    }  

    .history-time {  
        font-size: 0.9rem;  
        color: #666;  
    }  

    .clear-history-btn {  
        width: 100%;  
        padding: 14px;  
        background: #dc3545;  
        color: #ffffff;  
        border: none;  
        border-radius: 12px;  
        font-size: 1rem;  
        font-weight: 600;  
        cursor: pointer;  
        font-family: 'Manrope', sans-serif;  
        margin-top: 20px;  
        transition: all 0.3s ease;  
    }  

    .clear-history-btn:hover {  
        background: #c82333;  
        transform: translateY(-2px);  
    }  

    .footer {  
        text-align: center;  
        padding: 30px 20px;  
        color: rgba(255, 255, 255, 0.9);  
        font-size: 0.95rem;  
        animation: fadeIn 0.6s ease-out 0.4s both;  
    }  

    .empty-state {  
        text-align: center;  
        padding: 40px 20px;  
        color: #999;  
        font-size: 1rem;  
    }  

    @keyframes fadeInDown {  
        from {  
            opacity: 0;  
            transform: translateY(-30px);  
        }  
        to {  
            opacity: 1;  
            transform: translateY(0);  
        }  
    }  

    @keyframes fadeInUp {  
        from {  
            opacity: 0;  
            transform: translateY(30px);  
        }  
        to {  
            opacity: 1;  
            transform: translateY(0);  
        }  
    }  

    @keyframes fadeIn {  
        from {  
            opacity: 0;  
        }  
        to {  
            opacity: 1;  
        }  
    }  

    @keyframes pulse {  
        0%, 100% {  
            box-shadow: 0 0 0 0 rgba(245, 87, 108, 0.7);  
        }  
        50% {  
            box-shadow: 0 0 0 20px rgba(245, 87, 108, 0);  
        }  
    }  

    @media (max-width: 768px) {  
        .header h1 {  
            font-size: 2.5rem;  
        }  

        .header p {  
            font-size: 1rem;  
        }  

        .main-card, .stats-section {  
            padding: 24px;  
        }  

        .click-area {  
            min-height: 280px;  
        }  

        .click-count {  
            font-size: 4rem;  
        }  

        .click-label {  
            font-size: 1.2rem;  
        }  

        .timer-display {  
            font-size: 1.5rem;  
        }  

        .instruction-text {  
            font-size: 1.1rem;  
        }  

        .timer-btn {  
            padding: 10px 20px;  
            font-size: 0.9rem;  
        }  

        .results {  
            grid-template-columns: 1fr 1fr;  
            gap: 12px;  
        }  

        .result-value {  
            font-size: 2rem;  
        }  

        .result-label {  
            font-size: 0.85rem;  
        }  

        .stats-title {  
            font-size: 1.5rem;  
        }  

        .best-score {  
            font-size: 2.5rem;  
        }  

        .history-score {  
            font-size: 1.3rem;  
        }  
    }  

    @media (max-width: 480px) {  
        body {  
            padding: 12px;  
        }  

        .header h1 {  
            font-size: 2rem;  
        }  

        .main-card, .stats-section {  
            padding: 20px;  
        }  

        .click-count {  
            font-size: 3.5rem;  
        }  

        .results {  
            grid-template-columns: 1fr;  
        }  
    }  

    ::-webkit-scrollbar {  
        width: 8px;  
    }  

    ::-webkit-scrollbar-track {  
        background: #f1f1f1;  
        border-radius: 10px;  
    }  

    ::-webkit-scrollbar-thumb {  
        background: #667eea;  
        border-radius: 10px;  
    }  

    ::-webkit-scrollbar-thumb:hover {  
        background: #5568d3;  
    }  
</style>

</head>  
<body>  
    <div class=\"container\">  
        <div class=\"header\">  
            <h1>CPS Counter</h1>  
            <p>Test your clicking speed and beat your personal best!</p>  
        </div>  <div class=\"main-card\">  
        <div class=\"timer-options\">  
            <button class=\"timer-btn active\" data-time=\"5\">5 Seconds</button>  
            <button class=\"timer-btn\" data-time=\"10\">10 Seconds</button>  
            <button class=\"timer-btn\" data-time=\"30\">30 Seconds</button>  
            <button class=\"timer-btn\" data-time=\"60\">60 Seconds</button>  
        </div>  

        <div class=\"click-area\" id=\"clickArea\">  
            <div class=\"instruction-text\">Click here to start!</div>  
        </div>  

        <div class=\"results\" id=\"results\" style=\"display: none;\">  
            <div class=\"result-card\">  
                <div class=\"result-value\" id=\"totalClicks\">0</div>  
                <div class=\"result-label\">Total Clicks</div>  
            </div>  
            <div class=\"result-card\">  
                <div class=\"result-value\" id=\"cpsScore\">0.0</div>  
                <div class=\"result-label\">CPS Score</div>  
            </div>  
            <div class=\"result-card\">  
                <div class=\"result-value\" id=\"avgCps\">0.0</div>  
                <div class=\"result-label\">Average CPS</div>  
            </div>  
        </div>  

        <button class=\"reset-btn\" id=\"resetBtn\" style=\"display: none;\">Try Again</button>  
    </div>  

    <div class=\"stats-section\">  
        <h2 class=\"stats-title\">Your Statistics</h2>  
          
        <div class=\"personal-best\">  
            <div class=\"best-score\" id=\"personalBest\">0.0</div>  
            <div class=\"best-label\">Personal Best CPS</div>  
        </div>  

        <div class=\"history-list\" id=\"historyList\">  
            <div class=\"empty-state\">No test history yet. Start clicking to create your first record!</div>  
        </div>  

        <button class=\"clear-history-btn\" id=\"clearHistoryBtn\" style=\"display: none;\">Clear History</button>  
    </div>  

    <div class=\"footer\">  
        <p>© 2024 CPS Counter. Improve your clicking speed and track your progress.</p>  
    </div>  
</div>  

<script>  
    // State Management  
    let clicks = 0;  
    let isTestActive = false;  
    let testStartTime = null;  
    let timerInterval = null;  
    let selectedTime = 5;  
    let clickTimestamps = [];  

    // DOM Elements  
    const clickArea = document.getElementById('clickArea');  
    const resultsDiv = document.getElementById('results');  
    const resetBtn = document.getElementById('resetBtn');  
    const totalClicksEl = document.getElementById('totalClicks');  
    const cpsScoreEl = document.getElementById('cpsScore');  
    const avgCpsEl = document.getElementById('avgCps');  
    const personalBestEl = document.getElementById('personalBest');  
    const historyListEl = document.getElementById('historyList');  
    const clearHistoryBtn = document.getElementById('clearHistoryBtn');  
    const timerButtons = document.querySelectorAll('.timer-btn');  

    // Initialize  
    loadPersonalBest();  
    loadHistory();  

    // Timer Selection  
    timerButtons.forEach(btn => {  
        btn.addEventListener('click', () => {  
            if (isTestActive) return;  
              
            timerButtons.forEach(b => b.classList.remove('active'));  
            btn.classList.add('active');  
            selectedTime = parseInt(btn.dataset.time);  
        });  
    });  

    // Click Area Handler  
    clickArea.addEventListener('click', handleClick);  

    function handleClick(e) {  
        if (!isTestActive) {  
            startTest();  
        }  
          
        if (isTestActive) {  
            registerClick();  
        }  
    }  

    function startTest() {  
        clicks = 0;  
        clickTimestamps = [];  
        isTestActive = true;  
        testStartTime = Date.now();  
          
        clickArea.classList.add('testing');  
        clickArea.innerHTML = `  
            <div class=\"click-count\" id=\"clickCount\">0</div>  
            <div class=\"click-label\">Clicks</div>  
            <div class=\"timer-display\" id=\"timerDisplay\">${selectedTime}s</div>  
        `;  
          
        updateTimer();  
        timerInterval = setInterval(updateTimer, 100);  
          
        setTimeout(endTest, selectedTime * 1000);  
    }  

    function registerClick() {  
        clicks++;  
        clickTimestamps.push(Date.now());  
        document.getElementById('clickCount').textContent = clicks;  
          
        // Visual feedback  
        const clickCount = document.getElementById('clickCount');  
        clickCount.style.transform = 'scale(1.1)';  
        setTimeout(() => {  
            clickCount.style.transform = 'scale(1)';  
        }, 100);  
    }  

    function updateTimer() {  
        const elapsed = (Date.now() - testStartTime) / 1000;  
        const remaining = Math.max(0, selectedTime - elapsed);  
        document.getElementById('timerDisplay').textContent = remaining.toFixed(1) + 's';  
    }  

    function endTest() {  
        clearInterval(timerInterval);  
        isTestActive = false;  
          
        const cps = (clicks / selectedTime).toFixed(2);  
        const avgCps = calculateAverageCPS();  
          
        clickArea.classList.remove('testing');  
        clickArea.classList.add('finished');  
        clickArea.innerHTML = `  
            <div class=\"click-count\">${clicks}</div>  
            <div class=\"click-label\">Total Clicks</div>  
            <div class=\"timer-display\">Test Complete!</div>  
        `;  
          
        totalClicksEl.textContent = clicks;  
        cpsScoreEl.textContent = cps;  
        avgCpsEl.textContent = avgCps.toFixed(2);  
          
        resultsDiv.style.display = 'grid';  
        resetBtn.style.display = 'block';  
          
        saveTestResult(parseFloat(cps), clicks);  
        updatePersonalBest(parseFloat(cps));  
    }  

    function calculateAverageCPS() {  
        if (clickTimestamps.length < 2) return 0;  
          
        let totalCPS = 0;  
        let intervals = 0;  
          
        for (let i = 1; i < clickTimestamps.length; i++) {  
            const interval = (clickTimestamps[i] - clickTimestamps[0]) / 1000;  
            if (interval > 0) {  
                totalCPS += i / interval;  
                intervals++;  
            }  
        }  
          
        return intervals > 0 ? totalCPS / intervals : 0;  
    }  

    function resetTest() {  
        clicks = 0;  
        clickTimestamps = [];  
        isTestActive = false;  
        testStartTime = null;  
          
        clickArea.classList.remove('testing', 'finished');  
        clickArea.innerHTML = '<div class=\"instruction-text\">Click here to start!</div>';  
          
        resultsDiv.style.display = 'none';  
        resetBtn.style.display = 'none';  
    }  

    resetBtn.addEventListener('click', resetTest);  

    // Local Storage Functions  
    function loadPersonalBest() {  
        const best = localStorage.getItem('cps_personal_best');  
        if (best) {  
            personalBestEl.textContent = parseFloat(best).toFixed(2);  
        }  
    }  

    function updatePersonalBest(cps) {  
        const currentBest = localStorage.getItem('cps_personal_best');  
        if (!currentBest || cps > parseFloat(currentBest)) {  
            localStorage.setItem('cps_personal_best', cps.toString());  
            personalBestEl.textContent = cps.toFixed(2);  
              
            // Celebration animation  
            personalBestEl.style.transform = 'scale(1.2)';  
            setTimeout(() => {  
                person
