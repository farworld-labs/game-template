# Farcade Game Template

A simple template for creating HTML5 games that can be played on Farcade. This template provides a basic setup with Phaser.js and Three.js, making it easy to create 2D and 3D games.

## Features

- 🎮 Pre-configured game container (max-width 400px; canvas ratio 500x800px)
- 🔍 Debug mode (toggle with Alt+D)
- 📦 Common game libraries included:
  - Phaser.js for 2D games
  - Three.js for 3D games
- 🎨 Clean, modern styling
- 📝 Single file setup - just edit index.html

## Getting Started

1. Copy the `index.html` file to your project
2. Open it in your browser to start developing
3. Edit the code in the `<script>` section to build your game

## Development

- The game container has a max-width of 400px by default, with a canvas size ratio of 500x800px.
- Use Alt+D to toggle debug mode
- All code goes in the single HTML file
- Libraries are loaded from CDN for simplicity

## Game Requirements

Your game should:

- Fit within the 500x800 canvas ratio
- Handle window resizing gracefully
- Work without requiring external resources
- Be playable with keyboard/mouse controls

## Add Farcade SDK

1. Add this script tag to load the SDK in the head section:
<script src="https://unpkg.com/@farcade/game-sdk@latest/dist/index.min.js"></script>

2. Add these SDK calls to the game (these are easy to add with ai prompting)

// When the game is fully loaded and ready to play:
window.FarcadeSDK.singlePlayer.actions.ready();

// When the game is over (replace scoreValue with the actual score):
window.FarcadeSDK.singlePlayer.actions.gameOver({ score: scoreValue });

// For haptic feedback on important interactions (like jumping or hitting obstacles):
window.FarcadeSDK.singlePlayer.actions.hapticFeedback();

// Add this to handle play again requests:
window.FarcadeSDK.on('play_again', () => {
// Reset the game state here
// For example: resetGame(), startNewGame(), etc.
});

// Add this to handle mute/unmute:
window.FarcadeSDK.on('toggle_mute', (data) => {
// Set game audio based on data.isMuted
// For example: setMuted(data.isMuted)
});

3. Make sure to call the ready event when the game is fully loaded and playable.
4. Call gameOver when the player loses or completes the game.
5. Add haptic feedback for important game events.

## Tips

- Use the debug utilities to log information:
  ```javascript
  debug.log('Your message here')
  ```
- The game container is centered on the page
- Common game libraries are pre-imported and ready to use
- Error handling is built-in
- You can uncomment the Three.js example code to start a 3D game

## Example Code

The template includes:

- Basic Phaser.js setup with physics
- Debug mode toggle
- Error handling
- Three.js setup (commented out)
- Responsive game container

## License

MIT
