# movies
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>MovieMania</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #0d0d0d;
            color: #fff;
        }

        header {
            background-color: #1c1c1c;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        header h1 {
            margin: 0;
            color: #ffcc00;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            margin-left: 20px;
        }

        nav a:hover {
            color: #ffcc00;
        }

        .hero {
            background: url('https://images.unsplash.com/photo-1606107557195-0e29a4b5b4aa') no-repeat center center/cover;
            height: 60vh;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .hero h2 {
            background: rgba(0, 0, 0, 0.6);
            padding: 1rem;
            font-size: 2.5rem;
            border-radius: 10px;
        }

        .movies {
            padding: 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
        }

        .movie-card {
            background: #1c1c1c;
            padding: 1rem;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s;
            cursor: pointer;
        }

        .movie-card:hover {
            transform: scale(1.05);
        }

        .movie-card img {
            width: 100%;
            border-radius: 10px;
        }

        .movie-card h3 {
            margin: 0.5rem 0 0.2rem;
        }

        .rating {
            color: #ffcc00;
        }

        footer {
            background: #111;
            text-align: center;
            padding: 1rem;
            font-size: 0.9rem;
            margin-top: 2rem;
        }

        a {
            color: #ffcc00;
            text-decoration: underline;
        }

        a:hover {
            color: #ffffff;
        }
    </style>
</head>

<body>

    <header>
        <h1>MovieMania</h1>
        <nav>
            <a href="#home">Home</a>
            <a href="#movies">Movies</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section class="hero" id="home">
        <h2>Welcome to MovieMania!</h2>
    </section>

    <section class="movies" id="movies">
        <div class="movie-card" data-video="https://www.youtube.com/embed/YoHD9XEInc0">
            <img src="https://m.media-amazon.com/images/M/MV5BMjExMjkwNTQ0Nl5BMl5BanBnXkFtZTcwNTY0OTk1Mw@@._V1_QL75_UX191_.jpg"
                alt="Inception">
            <h3>Inception</h3>
            <p class="rating">⭐ 8.8/10</p>
            <a href="https://www.youtube.com/watch?v=YoHD9XEInc0" target="_blank">▶ Click to Watch</a>
        </div>

        <div class="movie-card" data-video="https://www.youtube.com/embed/TcMBFSGVi1c">
            <img src="https://m.media-amazon.com/images/I/71niXI3lxlL._AC_SL1024_.jpg" alt="Avengers: Endgame">
            <h3>Avengers: Endgame</h3>
            <p class="rating">⭐ 8.4/10</p>
            <a href="https://www.youtube.com/watch?v=TcMBFSGVi1c" target="_blank">▶ Click to Watch</a>
        </div>

        <div class="movie-card" data-video="https://www.youtube.com/embed/zSWdZVtXT7E">
            <img src="https://m.media-amazon.com/images/I/81c+9BOQNWL._AC_SY679_.jpg" alt="Interstellar">
            <h3>Interstellar</h3>
            <p class="rating">⭐ 8.6/10</p>
            <a href="https://www.youtube.com/watch?v=zSWdZVtXT7E" target="_blank">▶ Click to Watch</a>
        </div>

        <div class="movie-card" data-video="https://www.youtube.com/embed/EXeTwQWrcwY">
            <img src="https://m.media-amazon.com/images/M/MV5BNDc1NDI4NTg2Nl5BMl5BanBnXkFtZTcwNTUxODA4MQ@@._V1_QL75_UX240_.jpg" alt="The Dark Knight">
            <h3>The Dark Knight</h3>
            <p class="rating">⭐ 9.0/10</p>
            <a href="https://www.youtube.com/watch?v=EXeTwQWrcwY" target="_blank">▶ Click to Watch</a>
        </div>
    </section>

    <section id="contact" style="padding: 2rem; text-align: center;">
        <h2>Contact Us</h2>
        <p>Email: contact@moviemania.com</p>
        <p>Instagram: @moviemania</p>
    </section>

    <!-- Video Modal -->
    <div id="videoModal"
        style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.9); z-index:1000; justify-content:center; align-items:center;">
        <div style="position:relative; width:90%; max-width:800px;">
            <iframe id="videoFrame" width="100%" height="450" frameborder="0" allowfullscreen></iframe>
            <button onclick="closeModal()"
                style="position:absolute; top:-15px; right:-15px; background:#ff0000; color:white; border:none; padding:0.5rem 1rem; border-radius:50%; font-size:1.2rem; cursor:pointer;">×</button>
        </div>
    </div>

    <footer>
        &copy; 2025 MovieMania. All rights reserved.
    </footer>

    <script>
        // Smooth scroll
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) target.scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Time-based greeting
        const greeting = document.querySelector('.hero h2');
        const hours = new Date().getHours();
        if (hours < 12) greeting.textContent = 'Good Morning! Welcome to MovieMania!';
        else if (hours < 18) greeting.textContent = 'Good Afternoon! Welcome to MovieMania!';
        else greeting.textContent = 'Good Evening! Welcome to MovieMania!';

        // Modal player
        const modal = document.getElementById('videoModal');
        const frame = document.getElementById('videoFrame');

        document.querySelectorAll('.movie-card').forEach(card => {
            card.addEventListener('click', () => {
                const videoUrl = card.getAttribute('data-video');
                frame.src = videoUrl + "?autoplay=1";
                modal.style.display = "flex";
            });
        });

        function closeModal() {
            modal.style.display = "none";
            frame.src = "";
        }

        window.addEventListener('click', function (e) {
            if (e.target === modal) closeModal();
        });
    </script>

</body>

</html>
