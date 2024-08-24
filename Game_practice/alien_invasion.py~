import sys, pygame
from settings import Settings
from shape import Ship
from bullet import Bullet
from alien import Alien

class AlienInvasion:
    def __init__(self):
        pygame.init();
        self.screen = pygame.display.set_mode((1200, 800));
        self.settings = Settings();
        pygame.display.set_caption("Space Invaders");
        self.ship = Ship(self);
        self.bullets = pygame.sprite.Group();
        self.fleet = pygame.sprite.Group();

        self._create_fleet();


    def _check_events(self):
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    sys.exit();
                elif event.type != pygame.QUIT:
                    if event.type == pygame.KEYDOWN:
                        self._check_kdwn(event);
                    elif event.type == pygame.KEYUP:
                        self._check_kup(event);

    def _check_kdwn(self, event):
        if event.key == pygame.K_RIGHT:
            self.ship.m_right = True;
        if event.key == pygame.K_LEFT:
            self.ship.m_left = True;
        if event.key == pygame.K_q:
            sys.exit();
        if event.key == pygame.K_SPACE:
            self._fire_bullet();

    def _check_kup(self, event):
        if event.key == pygame.K_RIGHT:
            self.ship.m_right = False;
        if event.key == pygame.K_LEFT:
            self.ship.m_left = False;
    
    def _fire_bullet(self):
        new_bullet = Bullet(self);
        if len(self.bullets) < self.settings.bullet_cap:
            self.bullets.add(new_bullet);

    def _create_fleet(self):
        alien = Alien(self);
        self.fleet.add(alien);

    def _update_screen(self):
            self.screen.fill(self.settings.bg_color);
            self.ship.blitme();
            for bullet in self.bullets.sprites():
                bullet.draw_bullet();
            self.fleet.draw(self.screen);
            pygame.display.flip();

    def run(self):
        while True:
            self._check_events();
            self.ship.update();
            self.bullets.update();
            self._update_screen();

if __name__ == "__main__":
    ai = AlienInvasion();
    ai.run();


