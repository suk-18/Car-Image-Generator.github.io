**Car-Image-Generator**:-

This is a simple web application project which is made with the help pf HTML,CSS and JS which generates the car images.
This application uses the other api like here we have used Unsplash API to fetch the images of the cars.

**Direction to use:**-
We can use the app with the help of "Get car" button. This "Get car" button will help to fetch a random image of a car and display it on the screen.

**Code:-**
The code for ths application is present in index.html file.The s code is present in the style.css file and js code is present in the index.js file.
The code are as below:

**html**
```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>car Pics Generator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h3>car Pics Generator</h1>
        <button class="btn" id="btn">Get car</button>
        <div class="car-container">
            <img class="car-img">
            <h3 class="car-name">car Name</h3>
        </div>
    </div>
    <script src="index.js"></script>
</body>
</html>
```
The css code is in the  below:-

**CSS**
```body{
    margin: 0;
    display: flex;
    width: 100vw;
    height: 100vh;
    justify-content: center;
    background-color: aqua;
    align-items: center;
}

.container{
    background: aliceblue;
    border-radius: 10px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.3);
    text-align: center;
    padding: 10px;
    width: 450px;
    margin: 5px;
}

.btn{
    background-color: green;
    color: aliceblue;
    padding: 10px 30px;
    font-size: 16px;
    margin-bottom: 30px;
    border-radius: 6px;
    cursor: pointer;

}

.btn:disabled{
    background-color: gray;
    cursor: not-allowed;
}

.car-img{
    height: 300px;
    width: 300px;
    border-radius: 50%;
    border: 3px solid green;
}

.car-name{
    margin: 20px;
    background-color: green;
    color: aliceblue;
    padding: 10px;
    border-radius: 6px;
    font-size: 17px;
    font-weight: 600;
}

.car-container{
    display: none;
}
```
The js code is shown in the below:
**Js**
```const btn = document.getElementById("btn");
const carContainer = document.querySelector(".car-container");
const carImg = document.querySelector(".car-img");
const carName = document.querySelector(".car-name");

btn.addEventListener("click", async function () {
  try {
    carImg.src = "spinner.svg";
    const response = await fetch("https://api.unsplash.com/photos/random?client_id=CkFO60TcgMR858-Cf0V_iIXrNGaRMVGS17HJwh-0bNo&query=car");
    const data = await response.json();
    console.log(data)
    btn.innerText = "Get Cars";
    carContainer.style.display = "block";
    carImg.src = data.links.download;
    carName.innerText = data.alt_description;
  } catch (error) {
    console.log(error);
    btn.innerText = "Get car";
    carName.innerText = "An error happened, please try again";
  }
});
```


**Hosted Link**
https://suk-18.github.io/Car-Image-Generator.github.io/











