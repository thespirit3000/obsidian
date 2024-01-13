202401120817
Tags: #article 

---
# Main pygame file


```python
import pygame, os, time
from states.title_screen import Title

class Game():
    def __init__(self):
        pygame.init()
        self.GAME_W,self.GAME_H = 480, 270
        self.SCREEN_W,self.SCREEN_H = 960, 540
        self.game_canvas = pygame.Surface((self.GAME_W, self.GAME_H))
        self.screen = pygame.display.set_mode((self.SCREEN_W, self.SCREEN_H))
        self.running, self.playing = True, True
        self.actions = {"left" : False, "right" : False, "up" : False,"down" : False,"action1" : False,"action2" : False,"start" : False}
        self.dt,self.prev_time = 0,0
        self.state_stack = []
        self.load_assets()
        self.load_states()

    def game_loop(self):
        while self.playing:
            self.get_dt()
            self.get_events()
            self.update()
            self.render()   

    def get_events(self):
       for event in pygame.event.get():
           if event == pygame.QUIT:
               self.playing = False
               self.running = False
           if event.type == pygame.KEYDOWN:
               if event.key == pygame.K_ESCAPE:
                   self.playing = False
                   self.running = False
               if event.key == pygame.K_a:
                   self.actions['left'] = True
               if event.key == pygame.K_d:
                   self.actions['right'] = True
               if event.key == pygame.K_w:
                   self.actions['up'] = True
               if event.key == pygame.K_s:
                   self.actions['down'] = True
               if event.key == pygame.K_p:
                   self.actions['action1'] = True
               if event.key == pygame.K_o:
                   self.actions['action2'] = True
               if event.key == pygame.K_RETURN:
                   self.actions['start'] = True

    def update(self):
        self.state_stack[-1].update(self.dt, self.actions)
        pass

    def render(self):
        self.state_stack[-1].render(self.game_canvas)
        self.screen.blit(pygame.transform.scale(self.game_canvas,(self.SCREEN_W,self.SCREEN_H)),(0,0))
        pygame.display.flip()
            
    def get_dt(self):
        now = time.time()
        self.dt = now - self.prev_time
        self.prev_time = now 

    def draw_text(self, surface, text, color, x, y):
        text_surface = self.font.render(text, True, color)
        text_rect = text_surface.get_rect(center=(x,y))
        surface.blit(text_surface, text_rect)

    def load_assets(self):
        self.assets_dir = os.path.join("assets")
        self.sprite_dir = os.path.join(self.assets_dir, "sprites")
        self.font_dir = os.path.join(self.assets_dir, "font")
        self.font = pygame.font.Font(os.path.join(self.font_dir,  "PressStart2P-vaV7.ttf"), 20)

    def load_states(self):
        self.title_screen = Title(self)
        self.state_stack.append(self.title_screen)

    def reset_keys(self):
        for action in self.actions:
            self.actions[action] = False

if __name__ == "__main__":
    g = Game()
    while g.running:
        g.game_loop()

```
---
### Zero-links

- [[00 Python]]
- [[00  Разработка]]

---
### Links

-