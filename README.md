# testRepo
// function for time difference
function diffSubtract(date1, date2) {
    return date2 - date1;
}
 
let end_date = {
    "full_year": "2023", // year
    "month": "01", // month number
    "day": "01", // day
    "hours": "00", // hours
    "minutes": "00", // minutes
    "seconds": "00" // seconds
}
 
// until the New Year left  
let end_date_str = `${end_date.full_year}-${end_date.month}-${end_date.day}T${end_date.hours}:${end_date.minutes}:${end_date.seconds}`;

// start timer
timer = setInterval(function () {
    // now date
    let now = new Date();
    let date = new Date(end_date_str);
    // difference
    let ms_left = diffSubtract(now, date);
    // if difference <= 0
    if (ms_left <= 0) { // То
        // turn off timer
        clearInterval(timer);
        alert("Happy New Year");
    } else { 
        let res = new Date(ms_left);
        // answer
        let str_timer = `${res.getUTCMonth()} monts ${res.getUTCDate() - 1} days ${res.getUTCHours()} hours`;
        // print time
        console.log("Until the New Year left: ",str_timer);
    }
}, 10000);
