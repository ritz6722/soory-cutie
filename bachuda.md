```python
from IPython.display import HTML, display

# Fixed version - NO emoji encoding issues for Jupyter!
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sorry Lucky - From Your Bestie</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
            padding: 20px;
        }
        
        body::before {
            content: '';
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-image: 
                radial-gradient(circle at 20% 80%, rgba(255,182,193,0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255,182,193,0.3) 0%, transparent 50%);
            animation: float 20s ease-in-out infinite;
            z-index: -1;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 1;
        }
        
        .header {
            margin-bottom: 40px;
            animation: fadeInUp 1s ease-out;
        }
        
        .header h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3.5rem;
            font-weight: 700;
            color: #ff6b9d;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            margin-bottom: 10px;
            animation: heartbeat 2s ease-in-out infinite;
        }
        
        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        
        .header p {
            font-size: 1.2rem;
            color: #333;
            font-weight: 300;
        }
        
        .apology-card {
            background: rgba(255,255,255,0.95);
            border-radius: 25px;
            padding: 40px 30px;
            margin: 30px 0;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255,107,157,0.3);
            animation: fadeInUp 1.2s ease-out 0.2s both;
        }
        
        .apology-card h2 {
            font-family: 'Dancing Script', cursive;
            font-size: 2.2rem;
            color: #ff6b9d;
            margin-bottom: 20px;
        }
        
        .apology-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #444;
            margin-bottom: 30px;
            font-weight: 300;
        }
        
        .emotions {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin: 30px 0;
        }
        
        .emotion-bubble {
            background: linear-gradient(135deg, #ff9a9e, #fecfef);
            padding: 15px 25px;
            border-radius: 50px;
            font-size: 1rem;
            color: #fff;
            font-weight: 600;
            box-shadow: 0 8px 20px rgba(255,107,157,0.3);
            animation: wiggle 2s ease-in-out infinite;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
        }
        
        .emotion-bubble:hover {
            transform: scale(1.1);
            box-shadow: 0 12px 30px rgba(255,107,157,0.5);
        }
        
        @keyframes wiggle {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(2deg); }
            75% { transform: rotate(-2deg); }
        }
        
        .promise-section {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            border-radius: 20px;
            padding: 35px;
            margin: 30px 0;
            animation: fadeInUp 1.4s ease-out 0.4s both;
        }
        
        .promise-section h3 {
            font-family: 'Dancing Script', cursive;
            font-size: 1.8rem;
            color: #ff6b9d;
            margin-bottom: 20px;
        }
        
        .promise-list {
            list-style: none;
            font-size: 1.1rem;
            color: #333;
            text-align: left;
        }
        
        .promise-list li {
            padding: 10px 0;
            position: relative;
            padding-left: 40px;
        }
        
        .promise-list li::before {
            content: '✨';
            position: absolute;
            left: 0;
            top: 10px;
            font-size: 1.5rem;
        }
        
        .hug-button {
            background: linear-gradient(135deg, #ff6b9d, #ff8fab);
            color: white;
            border: none;
            padding: 20px 50px;
            font-size: 1.3rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 15px 30px rgba(255,107,157,0.4);
            transition: all 0.3s ease;
            margin: 30px 0;
            animation: pulse 2s infinite;
        }
        
        .hug-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(255,107,157,0.6);
        }
        
        @keyframes pulse {
            0% { box-shadow: 0 15px 30px rgba(255,107,157,0.4); }
            50% { box-shadow: 0 15px 30px rgba(255,107,157,0.7); }
            100% { box-shadow: 0 15px 30px rgba(255,107,157,0.4); }
        }
        
        .floating-hearts {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            pointer-events: none;
            z-index: 10;
        }
        
        .heart {
            position: absolute;
            font-size: 2rem;
            color: #ff6b9d;
            animation: floatUp 6s linear infinite;
        }
        
        @keyframes floatUp {
            0% { opacity: 1; transform: translateY(100vh) rotate(0deg); }
            100% { opacity: 0; transform: translateY(-100px) rotate(360deg); }
        }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .footer {
            margin-top: 40px;
            font-size: 1.1rem;
            color: #666;
            font-style: italic;
            padding: 20px;
            background: rgba(255,255,255,0.5);
            border-radius: 15px;
        }
    </style>
</head>
<body>
    <div class="floating-hearts" id="heartsContainer"></div>
    
    <div class="container">
        <div class="header">
            <h1>Sorry Lucky</h1>
            <p>To my absolute favorite human, my bestie forever</p>
        </div>
        
        <div class="apology-card">
            <h2>Hey Lucky, my sweet girl...</h2>
            <div class="apology-text">
                I know I said something really dumb and it hurt your feelings. 
                I'm <strong>SO SORRY</strong> from the bottom of my heart. 
                You mean <strong>EVERYTHING</strong> to me and I hate that I made you sad. 
                You're my sunshine, my safe place, my everything. 
                Please forgive me?
                <br><br>
                I was wrong and I promise I'll do better. You're too precious to me!
            </div>
            
            <div class="emotions">
                <button class="emotion-bubble" onclick="createHearts()">Im so sorry</button>
                <button class="emotion-bubble" onclick="createHearts()">I love you</button>
                <button class="emotion-bubble" onclick="createHearts()">Big hug</button>
                <button class="emotion-bubble" onclick="createHearts()">Youre amazing</button>
                <button class="emotion-bubble" onclick="createHearts()">Forgive me</button>
            </div>
        </div>
        
        <div class="promise-section">
            <h3>My Promises To You</h3>
            <ul class="promise-list">
                <li>I'll always think before I speak</li>
                <li>I'll be more careful with your heart</li>
                <li>I'll make you laugh twice as much to make up for this</li>
                <li>I'll buy you ice cream (your favorite flavor!)</li>
                <li>I'll be your bestie forever and always</li>
                <li>I'll never hurt you again on purpose</li>
            </ul>
        </div>
        
        <button class="hug-button" onclick="sendHug()">
            SEND ME A VIRTUAL HUG
        </button>
        
        <div class="footer">
            P.S. You're the best thing that ever happened to me. 
            Don't stay mad at me too long!
            Love you to the moon and back!
        </div>
    </div>

    <script>
        function createHearts() {
            const container = document.getElementById('heartsContainer');
            for(let i = 0; i < 12; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.innerHTML = ['&hearts;', '&hearts;', '&#10084;', '&#9829;', '&#10052;', '&#10053;'][Math.floor(Math.random() * 6)];
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
                    container.appendChild(heart);
                    setTimeout(() => heart.remove(), 7000);
                }, i * 150);
            }
        }
        
        function sendHug() {
            createHearts();
            const button = document.querySelector('.hug-button');
            const originalText = button.innerHTML;
            button.innerHTML = 'HUG SENT! HUG SENT!';
            button.style.background = 'linear-gradient(135deg, #ffd700, #ffed4e)';
            setTimeout(() => {
                button.innerHTML = originalText;
                button.style.background = 'linear-gradient(135deg, #ff6b9d, #ff8fab)';
            }, 2500);
        }
        
        setTimeout(createHearts, 1000);
        setInterval(() => { if(Math.random() > 0.6) createHearts(); }, 7000);
    </script>
</body>
</html>
"""

# Display in Jupyter Notebook
display(HTML(html_content))

print("✅ FIXED! No more encoding errors!")
print("🎉 Emotional apology website LOADED perfectly!")
print("🖱️ Click pink buttons for heart explosions!")
print("🤗 Click HUG button for special golden effect!")
```



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sorry Lucky - From Your Bestie</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&display=swap');

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
            padding: 20px;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-image: 
                radial-gradient(circle at 20% 80%, rgba(255,182,193,0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255,182,193,0.3) 0%, transparent 50%);
            animation: float 20s ease-in-out infinite;
            z-index: -1;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 1;
        }

        .header {
            margin-bottom: 40px;
            animation: fadeInUp 1s ease-out;
        }

        .header h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3.5rem;
            font-weight: 700;
            color: #ff6b9d;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            margin-bottom: 10px;
            animation: heartbeat 2s ease-in-out infinite;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .header p {
            font-size: 1.2rem;
            color: #333;
            font-weight: 300;
        }

        .apology-card {
            background: rgba(255,255,255,0.95);
            border-radius: 25px;
            padding: 40px 30px;
            margin: 30px 0;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255,107,157,0.3);
            animation: fadeInUp 1.2s ease-out 0.2s both;
        }

        .apology-card h2 {
            font-family: 'Dancing Script', cursive;
            font-size: 2.2rem;
            color: #ff6b9d;
            margin-bottom: 20px;
        }

        .apology-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #444;
            margin-bottom: 30px;
            font-weight: 300;
        }

        .emotions {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin: 30px 0;
        }

        .emotion-bubble {
            background: linear-gradient(135deg, #ff9a9e, #fecfef);
            padding: 15px 25px;
            border-radius: 50px;
            font-size: 1rem;
            color: #fff;
            font-weight: 600;
            box-shadow: 0 8px 20px rgba(255,107,157,0.3);
            animation: wiggle 2s ease-in-out infinite;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
        }

        .emotion-bubble:hover {
            transform: scale(1.1);
            box-shadow: 0 12px 30px rgba(255,107,157,0.5);
        }

        @keyframes wiggle {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(2deg); }
            75% { transform: rotate(-2deg); }
        }

        .promise-section {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            border-radius: 20px;
            padding: 35px;
            margin: 30px 0;
            animation: fadeInUp 1.4s ease-out 0.4s both;
        }

        .promise-section h3 {
            font-family: 'Dancing Script', cursive;
            font-size: 1.8rem;
            color: #ff6b9d;
            margin-bottom: 20px;
        }

        .promise-list {
            list-style: none;
            font-size: 1.1rem;
            color: #333;
            text-align: left;
        }

        .promise-list li {
            padding: 10px 0;
            position: relative;
            padding-left: 40px;
        }

        .promise-list li::before {
            content: '✨';
            position: absolute;
            left: 0;
            top: 10px;
            font-size: 1.5rem;
        }

        .hug-button {
            background: linear-gradient(135deg, #ff6b9d, #ff8fab);
            color: white;
            border: none;
            padding: 20px 50px;
            font-size: 1.3rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 15px 30px rgba(255,107,157,0.4);
            transition: all 0.3s ease;
            margin: 30px 0;
            animation: pulse 2s infinite;
        }

        .hug-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(255,107,157,0.6);
        }

        @keyframes pulse {
            0% { box-shadow: 0 15px 30px rgba(255,107,157,0.4); }
            50% { box-shadow: 0 15px 30px rgba(255,107,157,0.7); }
            100% { box-shadow: 0 15px 30px rgba(255,107,157,0.4); }
        }

        .floating-hearts {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            pointer-events: none;
            z-index: 10;
        }

        .heart {
            position: absolute;
            font-size: 2rem;
            color: #ff6b9d;
            animation: floatUp 6s linear infinite;
        }

        @keyframes floatUp {
            0% { opacity: 1; transform: translateY(100vh) rotate(0deg); }
            100% { opacity: 0; transform: translateY(-100px) rotate(360deg); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .footer {
            margin-top: 40px;
            font-size: 1.1rem;
            color: #666;
            font-style: italic;
            padding: 20px;
            background: rgba(255,255,255,0.5);
            border-radius: 15px;
        }
    </style>
</head>
<body>
    <div class="floating-hearts" id="heartsContainer"></div>

    <div class="container">
        <div class="header">
            <h1>Sorry Lucky</h1>
            <p>To my absolute favorite human, my bestie forever</p>
        </div>

        <div class="apology-card">
            <h2>Hey Lucky, my sweet girl...</h2>
            <div class="apology-text">
                I know I said something really dumb and it hurt your feelings. 
                I'm <strong>SO SORRY</strong> from the bottom of my heart. 
                You mean <strong>EVERYTHING</strong> to me and I hate that I made you sad. 
                You're my sunshine, my safe place, my everything. 
                Please forgive me?
                <br><br>
                I was wrong and I promise I'll do better. You're too precious to me!
            </div>

            <div class="emotions">
                <button class="emotion-bubble" onclick="createHearts()">Im so sorry</button>
                <button class="emotion-bubble" onclick="createHearts()">I love you</button>
                <button class="emotion-bubble" onclick="createHearts()">Big hug</button>
                <button class="emotion-bubble" onclick="createHearts()">Youre amazing</button>
                <button class="emotion-bubble" onclick="createHearts()">Forgive me</button>
            </div>
        </div>

        <div class="promise-section">
            <h3>My Promises To You</h3>
            <ul class="promise-list">
                <li>I'll always think before I speak</li>
                <li>I'll be more careful with your heart</li>
                <li>I'll make you laugh twice as much to make up for this</li>
                <li>I'll buy you ice cream (your favorite flavor!)</li>
                <li>I'll be your bestie forever and always</li>
                <li>I'll never hurt you again on purpose</li>
            </ul>
        </div>

        <button class="hug-button" onclick="sendHug()">
            SEND ME A VIRTUAL HUG
        </button>

        <div class="footer">
            P.S. You're the best thing that ever happened to me. 
            Don't stay mad at me too long!
            Love you to the moon and back!
        </div>
    </div>

    <script>
        function createHearts() {
            const container = document.getElementById('heartsContainer');
            for(let i = 0; i < 12; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.innerHTML = ['&hearts;', '&hearts;', '&#10084;', '&#9829;', '&#10052;', '&#10053;'][Math.floor(Math.random() * 6)];
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
                    container.appendChild(heart);
                    setTimeout(() => heart.remove(), 7000);
                }, i * 150);
            }
        }

        function sendHug() {
            createHearts();
            const button = document.querySelector('.hug-button');
            const originalText = button.innerHTML;
            button.innerHTML = 'HUG SENT! HUG SENT!';
            button.style.background = 'linear-gradient(135deg, #ffd700, #ffed4e)';
            setTimeout(() => {
                button.innerHTML = originalText;
                button.style.background = 'linear-gradient(135deg, #ff6b9d, #ff8fab)';
            }, 2500);
        }

        setTimeout(createHearts, 1000);
        setInterval(() => { if(Math.random() > 0.6) createHearts(); }, 7000);
    </script>
</body>
</html>



    ✅ FIXED! No more encoding errors!
    🎉 Emotional apology website LOADED perfectly!
    🖱️ Click pink buttons for heart explosions!
    🤗 Click HUG button for special golden effect!
    


```python
# Add this to your notebook
from IPython.display import HTML

HTML("""
<a href="sorry_lucky.html" target="_blank" style="font-size:24px; padding:20px; background:#ff6b9d; color:white; text-decoration:none; border-radius:25px; display:inline-block;">
🌐 OPEN MY APOLOGY (Share this tab!)
</a>
""")
```





<a href="sorry_lucky.html" target="_blank" style="font-size:24px; padding:20px; background:#ff6b9d; color:white; text-decoration:none; border-radius:25px; display:inline-block;">
🌐 OPEN MY APOLOGY (Share this tab!)
</a>





```python

```
