### "# Bricker" ###

<img width="104" alt="paddle" src="https://github.com/inbarbahnof/Bricker/assets/158153825/73f11c2f-cca0-4d5e-99c1-2190cfbfc542">


Introducing an Arkanoid-inspired game developed using DanoGameLab, where bricks exhibit dynamic behaviors to enhance gameplay:

### Brick Behaviors: ###

Splitting Brick: Breaks into two smaller balls upon impact.
Secondary Paddle Brick: Creates a secondary paddle that mimics the original, disappearing after 4 ball collisions.
Camera Distortion Brick: Alters the main camera to follow the ball, reverting after 4 collisions.
Extra Life Brick: Drops an additional life for the player to collect.
Double Behavior Brick: Randomly assigns multiple behaviors to a single brick.

### Control Scheme: ###
Use the left and right arrow keys to move the paddle horizontally.

### Behavior implemantation: ###
To implement the various behaviors, I devised a class structure where each behavior is encapsulated within its own class, overriding the onCollision method with specific implementations tailored to each behavior's requirements. Additionally, I established a strategy factory responsible for generating strategies based on requested probabilities.

Here's a breakdown of the implementation:

Behavior Classes: Each behavior, such as splitting, secondary paddle creation, camera distortion, etc., is represented by a separate class that inherits from a common interface.

Factory Pattern: A factory class is responsible for creating strategies based on requested probabilities. For instance, there's a higher probability for regular strategies and a lower probability for special ones.

Interface: An interface defines the contract that each behavior class must adhere to, ensuring consistency across all implementations.
By organizing the behaviors into distinct classes and leveraging the factory pattern, the implementation becomes modular, extensible, and easy to maintain. This approach allows for seamless integration of new behaviors and fine-tuning of their probabilities to achieve the desired gameplay experience.

Double Strategy Implementation: To facilitate the implementation of the double strategy, it's managed within the factory. A variable named MAX_STRATEGIES dictates the maximum number of strategies a brick can acquire. By adjusting this variable (currently set to 3), you can control the variety of strategies assigned to each brick.
