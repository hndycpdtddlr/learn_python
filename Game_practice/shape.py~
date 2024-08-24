import pygame

class Ship:
    def __init__(self, ai_game):
        self.screen = ai_game.screen;
        self.screen_rect = ai_game.screen.get_rect();
        self.image = pygame.image.load("C:/Users/skipp/Python/Practice_proj/Game_practice/images/ship.bmp");
        self.rect = self.image.get_rect();
        self.rect.midbottom = self.screen_rect.midbottom;
        self.m_right = False;
        self.m_left = False;
        self.settings = ai_game.settings;
        self.x = float(self.rect.x);
        self.bullets = pygame.sprite.Group();

    def update(self):
        if self.m_right and self.rect.right < self.screen_rect.right:
                self.x += self.settings.ship_speed;
        if self.m_left and self.rect.left > 0:
                self.x -= self.settings.ship_speed;
        self.rect.x = self.x;

    def blitme(self):
        self.screen.blit(self.image, self.rect);
