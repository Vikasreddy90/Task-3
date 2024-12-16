<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Carousel</title>
    <style>
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f4f4f4;
            font-family: Arial, sans-serif;
        }
        .carousel-container {
            width: 300px;
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        img {
            width: 100%;
            display: none;
        }
        img.active {
            display: block;
        }
        .buttons {
            display: flex;
            justify-content: space-between;
            position: absolute;
            top: 50%;
            width: 100%;
            transform: translateY(-50%);
           
        }
        button {
            background-color: rgba(0, 0, 0, 0.6);
            color: white;
            border: none;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            cursor: pointer;
        }
        button:hover {
            background-color: rgba(0, 0, 0, 0.8);
        }
    </style>
</head>
<body>

    <div class="carousel-container">
        <img src="https://www.emp.ie/dw/image/v2/BBQV_PRD/on/demandware.static/-/Sites-storefront-emp/default/dwce291e7f/108341_MT_Header_Deadpool_2024_NEU.jpg?sw=500" class="active" alt="Image 1">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRkorq2HqFTFciMjRyyxAa4p-pG5D204eTb7Qpk4ZUOSW3-U6qL9AxpRLTzBp-8mmbjhqU&usqp=CAU" alt="Image 2">
        <img src="https://i.redd.it/o6kg91wr7na91.jpg" alt="Image 3">
        <div class="buttons">
            <button onclick="prevImage()">&#10094;</button>
            <button onclick="nextImage()">&#10095;</button>
        </div>
    </div>

    <script>
        let currentIndex = 0;
        const images = document.querySelectorAll('.carousel-container img');

        function showImage(index) {
            images.forEach((img, i) => {
                img.classList.toggle('active', i === index);
            });
        }

        function nextImage() {
            currentIndex = (currentIndex + 1) % images.length;
            showImage(currentIndex);
        }

        function prevImage() {
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            showImage(currentIndex);
        }
    </script>
</body>
</html>
