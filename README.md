
<!---
NICDA08/NICDA08 is a ✨ specialimport pygame
import random

# Initialize Pygame
pygame.init()

# Set up the game window
WIDTH = 800
HEIGHT = 600
window = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Shooter Game")

# Colors
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
RED = (255, 0, 0)

# Player
player_width = 50
player_height = 50
player_x = WIDTH // 2 - player_width // 2
player_y = HEIGHT - player_height - 10
player_speed = 5

# Bullet
bullet_width = 5
bullet_height = 15
bullet_speed = 7
bullets = []

# Enemy
enemy_width = 50
enemy_height = 50
enemy_speed = 2
enemies = []

# Game loop
clock = pygame.time.Clock()
running = True
score = 0

while running:
    clock.tick(60)
    
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.KEYDOWN:
            if event.key == pygame.K_SPACE:
                bullets.append([player_x + player_width // 2 - bullet_width // 2, player_y])

    # Move player
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and player_x > 0:
        player_x -= player_speed
    if keys[pygame.K_RIGHT] and player_x < WIDTH - player_width:
        player_x += player_speed

    # Move bullets
    for bullet in bullets[:]:
        bullet[1] -= bullet_speed
        if bullet[1] < 0:
            bullets.remove(bullet)

    # Spawn enemies
    if len(enemies) < 5 and random.randint(1, 100) == 1:
        enemies.append([random.randint(0, WIDTH - enemy_width), 0])

    # Move enemies
    for enemy in enemies[:]:
        enemy[1] += enemy_speed
        if enemy[1] > HEIGHT:
            enemies.remove(enemy)

    # Check for collisions
    for enemy in enemies[:]:
        for bullet in bullets[:]:
            if (enemy[0] < bullet[0] < enemy[0] + enemy_width and
                enemy[1] < bullet[1] < enemy[1] + enemy_height):
                enemies.remove(enemy)
                bullets.remove(bullet)
                score += 1
                break

    # Draw everything
    window.fill(BLACK)
    pygame.draw.rect(window, WHITE, (player_x, player_y, player_width, player_height))
    for bullet in bullets:
        pygame.draw.rect(window, WHITE, (bullet[0], bullet[1], bullet_width, bullet_height))
    for enemy in enemies:
        pygame.draw.rect(window, RED, (enemy[0], enemy[1], enemy_width, enemy_height))

    # Draw score
    font = pygame.font.Font(None, 36)
    score_text = font.render(f"Score: {score}", True, WHITE)
    window.blit(score_text, (10, 10))

    pygame.display.update()

pygame.quit()

 ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
