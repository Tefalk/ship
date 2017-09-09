from scene import *
import sound

class MyScene (Scene):
    def setup(self):
        self.background_color = 'midnightblue'
        self.ship = SpriteNode('spc:PlayerShip1Orange')
        self.ship.position = self.size / 2
        self.add_child(self.ship)

    def update(self):
        x, y, z = gravity()
        pos = self.ship.position
        pos += (x * 15, y * 15)
        # Don't allow the ship to move beyond the screen bounds:
        pos.x = max(0, min(self.size.w, pos.x))
        pos.y = max(0, min(self.size.h, pos.y))
        self.ship.position = pos

    def touch_began(self, touch):
        laser = SpriteNode('spc:LaserBlue9', position=self.ship.position, z_position=-1, parent=self)
        laser.run_action(Action.sequence(Action.move_by(0, 1000), Action.remove()))
        sound.play_effect('arcade:Laser_1')

run(MyScene(), PORTRAIT)
