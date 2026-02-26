# Tetris — Play.fun Edition

A classic Tetris game integrated with the **[Play.fun](https://play.fun)** play-to-earn platform on Solana blockchain.

## Features

- Classic Tetris gameplay with modern neon design
- Full **Play.fun Browser SDK** integration
- Points tracking via `addPoints()` and `endGame()`
- Responsive design with mobile touch controls
- Score, level, and line tracking
- Next piece preview
- Ghost grid for better visibility

## Play.fun Integration

This game uses the Play.fun Browser SDK to:

1. **Track points** — Every score increment is sent to Play.fun via `ogp.addPoints()`
2. **End game sessions** — When the game is over, `ogp.endGame()` is called to submit the final score
3. **Points widget** — The SDK's built-in points widget is enabled for real-time display

### Setup for Play.fun

1. Register your game at [play.fun](https://play.fun) and get your **Game ID** and **API Key**
2. Update the meta tags in `index.html`:
   ```html
   <meta name="playfun-verification" content="YOUR_WALLET_ADDRESS">
   <meta name="x-ogp-key" content="YOUR_API_KEY">
   ```
3. Update the `gameId` in the SDK initialization:
   ```javascript
   ogp.init({ gameId: 'YOUR_GAME_ID' });
   ```
4. Deploy to GitHub Pages and register the URL on Play.fun

## Controls

### Desktop
| Key | Action |
|-----|--------|
| ← | Move left |
| → | Move right |
| ↑ | Rotate |
| ↓ | Drop faster |
| ESC | End game |

### Mobile
Touch buttons are displayed at the bottom of the screen on mobile devices.

## Scoring

| Action | Points |
|--------|--------|
| Piece placed | 10 |
| 1 line cleared | 100 |
| 2 lines cleared | 200 |
| 3 lines cleared | 400 |
| 4 lines (Tetris!) | 800 |

## Deployment

### GitHub Pages

```bash
git init
git add .
git commit -m "Initial commit"
gh repo create tetris-playfun --public --source=. --push
```

Then enable GitHub Pages in repository settings.

## Credits

- Original Tetris logic based on [jakesgordon/javascript-tetris](https://github.com/jakesgordon/javascript-tetris)
- Integrated with [Play.fun](https://play.fun) platform SDK
- Neon design and mobile controls added for Play.fun compatibility

## License

MIT License
