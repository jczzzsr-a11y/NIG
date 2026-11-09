import json

# Define graphic parameters or dynamic data
config = {
    "title": "NEXUS INFRASTRUCTURE GROUP",
    "symbol": "< N >",
    "region": "US",
    "theme_color": "#00f0ff"
}

svg_content = f'''<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 400" width="100%">
  <defs>
    <linearGradient id="grad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#0b132b"/>
      <stop offset="50%" stop-color="#1c2541"/>
      <stop offset="100%" stop-color="#00f0ff"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <style>
    .symbol {{ font-family: monospace; font-weight: bold; font-size: 64px; fill: {config["theme_color"]}; filter: url(#glow); }}
    .title {{ font-family: sans-serif; font-weight: 800; font-size: 32px; fill: #ffffff; letter-spacing: 4px; }}
    .subtitle {{ font-family: sans-serif; font-size: 16px; fill: #8d99ae; letter-spacing: 2px; }}
    @keyframes pulse {{
      0% {{ opacity: 0.7; transform: scale(1); }}
      50% {{ opacity: 1; transform: scale(1.05); }}
      100% {{ opacity: 0.7; transform: scale(1); }}
    }}
    .animated-symbol {{ animation: pulse 3s infinite ease-in-out; transform-origin: center; }}
  </style>

  <rect width="100%" height="100%" fill="url(#grad)" rx="12"/>
  
  <g class="animated-symbol">
    <text x="50%" y="35%" dominant-baseline="middle" text-anchor="middle" class="symbol">{config["symbol"]}</text>
  </g>
  
  <text x="50%" y="60%" dominant-baseline="middle" text-anchor="middle" class="title">{config["title"]}</text>
  <text x="50%" y="75%" dominant-baseline="middle" text-anchor="middle" class="subtitle">POWERING MODERN CONNECTIVITY &amp; DEVELOPMENT • {config["region"]}</text>
</svg>
'''

with open("assets/banner.svg", "w", encoding="utf-8") as f:
    f.write(svg_content)

print("Dynamic SVG banner successfully generated.")
 