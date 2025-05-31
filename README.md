<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=0.5">
    <title>Go-ahead London</title>
    <style>
        body {
            background: linear-gradient(to left, blue, black, purple);
            opacity: 0.9;
            font-family: Arial, sans-serif;
            color: yellow;
            text-align: center;
        }
        .button {
            display: inline-block;
            margin: 4px;
            padding: 4px;
            font-size: 20px;
            color: white;
            background-color: transparent;
            border: 3px solid purple;
            border-radius: 6px;
            cursor: pointer;
            transition: transform 0.8s;
        }
        .button:hover {
            transform: scale(1.4);
        }
        #modal {
            display: none;
            position: fixed;
            top: 5px;
            left: 15px;
            width: 95%;
            height: 80%;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 1000;
        }
        #iframe {
            width: 89%;
            height: 59%;
            margin: 5% auto;
            display: block;
            border: 2px;
        }
        .animated-button {
            animation: bounce 1s infinite;
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-30px);
            }
            60% {
                transform: translateY(-15px);
            }
        }
    </style>
</head>
<body>

    <h1> Abellio - Transport UK</h1>
    <div>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 1021')"><h2> 1021</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2001')"><h2> 2001</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2013')"><h2> 2013</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2016')"><h2> 2016</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2420')"><h2> 2420</h2></button>
    </div>
    <div>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2438')"><h2> 2438</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2462')"><h2> 2462</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2605')"><h2> 2605</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2605')"><h2> 2605</h2></button>
    </div>
    <div>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2605')"><h2> 2605</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2609')"><h2> 2609</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 8152')"><h2> 8152</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 8583')"><h2> 8583</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 8877')"><h2> 8877</h2></button>
    </div>
    <div>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 8891')"><h2> 8891</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 9534')"><h2> 9534</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 9538')"><h2> 9538</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 9539')"><h2> 9539</h2></button>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab LT638')"><h2> LT638</h2></button>
    </div>

    <div id="modal">
        <marquee direction="random" scrollamount="15" behavior="alternate" style="width: 100%; height: 55px; font-size: 50px; font-family: Lucida Console; text-decoration: blink;"><img src='https://i.imgur.com/PgAe7fV.png' alt='' width="150px" height="50px"></marquee> 
        <iframe id="iframe" src=""></iframe>
        <button class="button" onclick="changeIframe('https://lvf.io/#LDN|Ab 2605')"><h1> 2605</h1></button>
        <marquee direction="left" scrollamount="8" behavior="alternate" style="width: 100%; height: 55px; font-size: 50px; font-family: Lucida Console; text-decoration: blink; border-style: groove;">21SA Field Service Engineer </marquee> 
    </div>

    <marquee direction="left" scrollamount="9" behavior="scroll" style="width: 100%; height: 200px;">    <button class="button animated-button" onclick="toggleMarqueeDirection()"><img src='https://i.imgur.com/LH8DpuK.gif' alt='' width="200px" height="200px"></button><button class="button animated-button" onclick="toggleMarqueeBehavior()"><img src='https://i.imgur.com/LH8DpuK.gif' alt='' width="200px" height="200px"></button></marquee>
    <marquee direction="right" scrollamount="9" behavior="scroll" style="width: 100%; height: 200px;">    <button class="button animated-button" onclick="toggleMarqueeDirection()"><img src='https://i.imgur.com/SXzObB0.gif' alt='' width="200px" height="200px"></button><button class="button animated-button" onclick="toggleMarqueeBehavior()"><img src='https://i.imgur.com/cD6WmQZ.gif' alt='' width="200px" height="200px"></button></marquee>
    <button class="button animated-button" onclick="toggleMarqueeDirection()">Toggle Marquee Direction</button>
    <button class="button animated-button" onclick="toggleMarqueeBehavior()">Toggle Marquee Behavior</button>

    <script>
        let marqueeDirection = 'left';
        let marqueeBehavior = 'scroll';

        function changeIframe(url) {
            try {
                const iframe = document.getElementById('iframe');
                iframe.src = url;
                document.getElementById('modal').style.display = 'block';
            } catch (error) {
                console.error("An error occurred while changing the iframe source: ", error);
                alert("Failed to load the content. Please try again later.");
            }
        }

        function toggleMarqueeDirection() {
            marqueeDirection = (marqueeDirection === 'left') ? 'right' : 'left';
            updateMarquee();
        }

        function toggleMarqueeBehavior() {
            marqueeBehavior = (marqueeBehavior === 'scroll') ? 'alternate' : 'scroll';
            updateMarquee();
        }

        function updateMarquee() {
            const marquee = document.querySelector('#modal marquee');
            marquee.setAttribute('direction', marqueeDirection);
            marquee.setAttribute('behavior', marqueeBehavior);
        }

        // Close modal when clicking outside of the iframe
        document.getElementById('modal').onclick = function() {
            this.style.display = 'none';
            document.getElementById('iframe').src = ''; // Clear the iframe source
        };
    </script>

</body>
</html>
