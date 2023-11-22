import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up display
width, height = 800, 600
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Simple Game")

# Set up colors
white = (255, 255, 255)
red = (255, 0, 0)

# Set up player
player_size = 50
player_x = width // 2 - player_size // 2
player_y = height - 2 * player_size

# Set up clock
clock = pygame.time.Clock()

# Main game loop
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and player_x > 0:
        player_x -= 5
    if keys[pygame.K_RIGHT] and player_x < width - player_size:
        player_x += 5

    # Update display
    screen.fill(white)
    pygame.draw.rect(screen, red, (player_x, player_y, player_size, player_size))

    pygame.display.flip()

    # Cap the frame rate
    clock.tick(30)
    keys = pygame.key.get_pressed()
if keys[pygame.K_LEFT] and player_x > 0:
    player_x -= 5
if keys[pygame.K_RIGHT] and player_x < width - player_size:
    player_x += 5

# Update display
screen.fill(white)
pygame.draw.rect(screen, red, (player_x, player_y, player_size, player_size))

pygame.display.flip()

# Cap the frame rate
clock.tick(30)
