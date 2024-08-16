![image](https://github.com/user-attachments/assets/b4a3b2e3-a775-4611-bfb2-7985f33c25fe)


# The-Melon-Man

The goal is to jump through randomly-generated platforms and get as high as possible.
Use space to jump, and A, D or arrows to move left / right.

[> DEMO <](https://hoangho0311.github.io/The-Melon-Man/)

# For contributors
1. Change character
2. Add double Jump
3. Add fireballs falling
   
## How to add a new platform?
1. Add a new texture: modify textures.png file, where each texture is 24 pixels high and wide. (You can add new ones wherever you want)
2. Specify the platform's structure and add it to the generator:
    - Open the generator.js file and add a new structure to array of structures:
      ```javascript
      game.structures = [
        ...,
        "newPlatform" : [{tileColumn: 3, tileRow: 2, x: 0, y: 0}, {tileColumn: 4, tileRow: 2, x: 1, y: 0}, ...]
      ]
      // tileColumn and tileRow are coordinates in textures.png file (starting from 0), and x & y are coordinates in game
      ```
    - After that you can tell the generator where to place your platform:
      ```javascript
      game.generateMap = function () {
        ...
        // Generate 20 plaforms starting from y = -15 to y = -75 with random x ranging from 0 to 8
       for (var i = 5; i < 25; i++) {
        this.map.structures.push({
          name: "newPlatform",
          x: Math.floor(Math.random() * 8),
          y: -i * 3
         })
       }
      }
      ```  



