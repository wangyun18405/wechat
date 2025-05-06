
                        <!DOCTYPE html>
                        <html lang="en">
                        <head>
                            <meta charset="UTF-8">
                            <meta name="viewport" content="width=device-width, initial-scale=1.0">
							<style>
								body {
									background-color: white; /* Ensure the iframe has a white background */
								}

								
        body {
            margin: 0;
            overflow: hidden;
            background-color: #000;
            color: #fff;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
        }
        h1 {
            font-size: 3em;
            z-index: 2;
        }
        canvas {
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }
    

							</style>
                        </head>
                        <body>
                            <!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>表白烟花</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #000;
            color: #fff;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
        }
        h1 {
            font-size: 3em;
            z-index: 2;
        }
        canvas {
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }
    </style>
</head>
<body>
    <h1>我喜欢你！</h1>
    <canvas id="fireworks"></canvas>
    <script>
        const canvas = document.getElementById('fireworks');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const fireworks = [];
        const particles = [];

        class Firework {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = canvas.height;
                this.speed = Math.random() * 3 + 2;
                this.angle = Math.random() * Math.PI / 4 - Math.PI / 8;
                this.color = `hsl(${Math.random() * 360}, 100%, 50%)`;
            }

            update() {
                this.x += Math.sin(this.angle) * this.speed;
                this.y -= Math.cos(this.angle) * this.speed;
                if (this.y < Math.random() * canvas.height / 2) {
                    this.explode();
                    fireworks.splice(fireworks.indexOf(this), 1);
                }
            }

            explode() {
                for (let i = 0; i < 50; i++) {
                    particles.push(new Particle(this.x, this.y, this.color));
                }
            }

            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, 2, 0, Math.PI * 2);
                ctx.fillStyle = this.color;
                ctx.fill();
            }
        }

        class Particle {
            constructor(x, y, color) {
                this.x = x;
                this.y = y;
                this.color = color;
                this.speed = Math.random() * 3 + 1;
                this.angle = Math.random() * Math.PI * 2;
                this.gravity = 0.05;
                this.opacity = 1;
            }

            update() {
                this.x += Math.sin(this.angle) * this.speed;
                this.y += Math.cos(this.angle) * this.speed + this.gravity;
                this.opacity -= 0.02;
                if (this.opacity <= 0) {
                    particles.splice(particles.indexOf(this), 1);
                }
            }

            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, 1, 0, Math.PI * 2);
                ctx.fillStyle = `rgba(${this.color}, ${this.opacity})`;
                ctx.fill();
            }
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            if (Math.random() < 0.05) {
                fireworks.push(new Firework());
            }
            fireworks.forEach(firework => {
                firework.update();
                firework.draw();
            });
            particles.forEach(particle => {
                particle.update();
                particle.draw();
            });
            requestAnimationFrame(animate);
        }

        animate();
    </script>
</body>
</html>



							<script>
                            	
        const canvas = document.getElementById('fireworks');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const fireworks = [];
        const particles = [];

        class Firework {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = canvas.height;
                this.speed = Math.random() * 3 + 2;
                this.angle = Math.random() * Math.PI / 4 - Math.PI / 8;
                this.color = `hsl(${Math.random() * 360}, 100%, 50%)`;
            }

            update() {
                this.x += Math.sin(this.angle) * this.speed;
                this.y -= Math.cos(this.angle) * this.speed;
                if (this.y < Math.random() * canvas.height / 2) {
                    this.explode();
                    fireworks.splice(fireworks.indexOf(this), 1);
                }
            }

            explode() {
                for (let i = 0; i < 50; i++) {
                    particles.push(new Particle(this.x, this.y, this.color));
                }
            }

            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, 2, 0, Math.PI * 2);
                ctx.fillStyle = this.color;
                ctx.fill();
            }
        }

        class Particle {
            constructor(x, y, color) {
                this.x = x;
                this.y = y;
                this.color = color;
                this.speed = Math.random() * 3 + 1;
                this.angle = Math.random() * Math.PI * 2;
                this.gravity = 0.05;
                this.opacity = 1;
            }

            update() {
                this.x += Math.sin(this.angle) * this.speed;
                this.y += Math.cos(this.angle) * this.speed + this.gravity;
                this.opacity -= 0.02;
                if (this.opacity <= 0) {
                    particles.splice(particles.indexOf(this), 1);
                }
            }

            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, 1, 0, Math.PI * 2);
                ctx.fillStyle = `rgba(${this.color}, ${this.opacity})`;
                ctx.fill();
            }
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            if (Math.random() < 0.05) {
                fireworks.push(new Firework());
            }
            fireworks.forEach(firework => {
                firework.update();
                firework.draw();
            });
            particles.forEach(particle => {
                particle.update();
                particle.draw();
            });
            requestAnimationFrame(animate);
        }

        animate();
    

							</script>
                        </body>
                        </html>
                    
