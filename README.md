#SPLASH-SCREEN
import pygame, sys
from pygame.locals import *

pygame.init()
windowSurface = pygame.display.set_mode((500,400), 0, 32)
pygame.display.set_caption('The Forest of Riddles')

BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
BLUE = (0, 0, 255)

basicFont = pygame.font.SysFont(None, 48)
text = basicFont.render('Forest of Riddles', True, WHITE, RED)
textRect = text.get_rect()
textRect.centerx = windowSurface.get_rect().centerx
textRect.centery = windowSurface.get_rect().centery

windowSurface.fill(WHITE)
pygame.draw.polygon(windowSurface, GREEN, ((146, 0), (291, 106), (236, 277), (56, 277), (0, 106)))
pygame.draw.polygon(windowSurface, GREEN, ((146, 0), (291,106), (236, 277), (56, 277), (100, 106)))
pygame.draw.rect(windowSurface, RED, (textRect.left - 20, textRect.top - 20, textRect.width + 40, textRect.height + 40))
pixArray = pygame.PixelArray(windowSurface)

pixArray[480][380] = BLACK
del pixArray

windowSurface.blit(text, textRect)
pygame.display.update()

while True:
    for event in pygame.event.get():
        if event.type == QUIT:
            pygame.quit()
            sys.exit()
