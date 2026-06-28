### 1. **CSS Scroll-Stack Animations**
```
<!Doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Stacking Cards Scroll Effect</title>
    <style>
        :root {
            --card-height: 580px;
            --card-margin: 40px;
            --bg-color: #0f172a;
        }

        body {
            background-color: var(--bg-color);
            margin: 0;
            padding: 0;
            font-family: system-ui, -apple-system, sans-serif;
        }

        /* Spacer to allow for scrolling before the effect starts */
        .spacer {
            height: 50vh;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
        }

        .stack {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: var(--card-margin);
            padding-bottom: 80vh; /* Extra space at bottom to finish last card animation */
            perspective: 1200px; 
        }

        .card {
            position: sticky;
            width: min(950px, 90%);
            height: var(--card-height);
            background: #1e293b;
            border-radius: 30px;
            overflow: hidden;
            transform-style: preserve-3d;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5);
            
            /* Scroll-Driven Animation Setup */
            view-timeline-name: --item-timeline;
            view-timeline-axis: block;
            animation: stack linear both;
            animation-timeline: --item-timeline;
            animation-range: exit 0% exit 100%;
        }

        /* Unique top offsets to keep cards visible as they stack */
        #card-1 { top: calc(var(--card-margin) * 1); }
        #card-2 { top: calc(var(--card-margin) * 2); }
        #card-3 { top: calc(var(--card-margin) * 3); }
        #card-4 { top: calc(var(--card-margin) * 4); }

        @keyframes stack {
            0% {
                transform: translateY(0) scale(1);
            }
            35% {
                transform: translateY(-10%) translateZ(-100px) rotateX(15deg) scale(0.95);
            }
            70% {
                transform: translateY(-20%) translateZ(-200px) rotateX(10deg) scale(0.9);
            }
            100% {
                transform: translateY(-30%) translateZ(-300px) scale(0.85);
                opacity: 0.5;
            }
        }

        /* Content Styling */
        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .info {
            position: absolute;
            inset: auto 0 0 0;
            padding: 40px;
            background: linear-gradient(transparent, rgba(0,0,0,0.9));
            color: white;
            backdrop-filter: blur(8px);
        }

        .info h2 {
            margin: 0 0 10px 0;
            font-size: 2rem;
        }

        .info p {
            margin: 0;
            opacity: 0.8;
            line-height: 1.6;
        }
    </style>
</head>
<body>

    <div class="spacer">
        <h1>Scroll Down to See the Magic ↓</h1>
    </div>

    <section class="stack">
        <article class="card" id="card-1">
            <img src="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?auto=format&fit=crop&q=80&w=1000" alt="Nature">
            <div class="info">
                <h2>The Mountain Mist</h2>
                <p>Experience the serene beauty of the high peaks where the air is fresh and the views are endless.</p>
            </div>
        </article>

        <article class="card" id="card-2">
            <img src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?auto=format&fit=crop&q=80&w=1000" alt="Forest">
            <div class="info">
                <h2>Deep Forest Paths</h2>
                <p>Wander through ancient groves where every tree has a story to tell and sunlight dances on the leaves.</p>
            </div>
        </article>

        <article class="card" id="card-3">
            <img src="https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&q=80&w=1000" alt="Lake">
            <div class="info">
                <h2>Crystal Clear Waters</h2>
                <p>Reflect on life by the side of still waters that mirror the sky in perfect clarity.</p>
            </div>
        </article>

        <article class="card" id="card-4">
            <img src="https://images.unsplash.com/photo-1447752875215-b2761acb3c5d?auto=format&fit=crop&q=80&w=1000" alt="Park">
            <div class="info">
                <h2>Autumn Whispers</h2>
                <p>As the leaves turn gold and red, the world prepares for a season of quiet transformation.</p>
            </div>
        </article>
    </section>

    <div class="spacer">
        <p>End of the Stack</p>
    </div>

</body>
</html>
```

### 2. Glass morphism card effect
 
 `.card { backdrop-filter: blur(16px) saturate(180%); -webkit-backdrop-filter: blur(16px) saturate(180%); background-color: rgba(17, 25, 40, 0.75); border-radius: 12px; border: 1px solid rgba(255, 255, 255, 0.125); }`
