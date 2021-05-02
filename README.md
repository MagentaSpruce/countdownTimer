# countdownTimer
Programmable countdown timer using HTML, CSS, and JS
This project is a programmable countdown timer which can be utilized multi-purposely and with easily changeable dates. Constructing this project has helped me to better practice and understand the following.

1) Using defer with my JS script
2) Flexbox
3) Creating and implementing functional logic
4) DOM manipulation

A general walkthrough of the JavaScript code is below:

First the elements were selected.
```JavaScript
const daysEl = document.getElementById('days');
const hoursEl = document.getElementById('hours');
const minsEl = document.getElementById('mins');
const secondsEl = document.getElementById('seconds');

const newYears = '1 Jan 2022';
```

Next the countdown function was created. 
```JavaScript
function countdown(){
    const newYearsDate = new Date(newYears);
    const currentDate = new Date();
    const totalSeconds = (newYearsDate - currentDate) / 1000;
    const days = Math.floor( (totalSeconds / 3600 / 24));
    const hours = Math.floor(totalSeconds / 3600) % 24;
    const mins = Math.floor(totalSeconds / 60) % 60;
    const seconds = Math.floor(totalSeconds) % 60;
```

Next the JavaScript is dynamically inserted into the HTML.
```JavaScript
daysEl.innerHTML = days;
hoursEl.innerHTML = formatTime(hours);
minsEl.innerHTML = formatTime(mins);
secondsEl.innerHTML = formatTime(seconds);
```

A format time function was added to insert a 0 when less than 10.
```JavaScript
function formatTime(time) {
    return time < 10 ? (`0${time}`) : time;
}
```

***End Walkthrough
