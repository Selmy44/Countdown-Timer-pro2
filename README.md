# Countdown-Timer-pro2
This is countdown timer pro2 web
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Countdown Timer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }

        #countdown {
            font-size: 36px;
            font-weight: bold;
            color: #333;
        }
    </style>
</head>
<body>
    <h1>Countdown Timer</h1>
    <div id="countdown">00:00:00</div>

    <script>
        function startCountdown(durationInSeconds) {
            let timer = durationInSeconds;
            const countdownElement = document.getElementById('countdown');

            function updateCountdown() {
                const hours = Math.floor(timer / 3600);
                const minutes = Math.floor((timer % 3600) / 60);
                const seconds = timer % 60;

                countdownElement.textContent = `${formatTime(hours)}:${formatTime(minutes)}:${formatTime(seconds)}`;

                if (timer > 0) {
                    timer--;
                } else {
                    clearInterval(intervalId);
                    alert('Countdown is over!');
                }
            }

            function formatTime(time) {
                return time < 10 ? `0${time}` : time;
            }

            updateCountdown(); // Initial call to display the full time

            const intervalId = setInterval(updateCountdown, 1000);
        }

        // Start the countdown with a duration of 5 minutes (300 seconds)
        startCountdown(300);
    </script>
</body>
</html>
