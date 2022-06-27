import pygame 
from sys import exit
from pygame.locals import *
import webbrowser
import os

# Oop function
class Open_file():
    def menu(self,image,location,x,y):
        self.image=image
        self.x=x
        self.y=y
        self.location=location
        mouse_pos = pygame.mouse.get_pos()
        image=pygame.image.load(self.image).convert_alpha()
        rect=image.get_rect(midbottom = (self.x,self.y))
        screen.blit(image,rect) # Import "Hello world" logo on screen
        if pygame.mouse.get_pressed()[0] and rect.collidepoint(mouse_pos):
            os.startfile(self.location) # Open file 

        for event in pygame.event.get():
               keys = pygame.key.get_pressed()
               if event.type == pygame.QUIT or keys[K_ESCAPE]:
                   exit() # Setting press Esc to exit     

        pygame.display.update()
        pygame.time.Clock().tick(60)

# Menu 2
def Sub_menu():
    pygame.mixer.unpause()
    running=True
    exit=pygame.image.load('Picture/exit.png').convert_alpha() # Import "Exit" logo 
    exit_rect=exit.get_rect(midbottom=(1300 ,780)) # Image  "Exit" logo rectangular (x,y) 
    text=pygame.font.Font('font/FFF_Tusj.ttf',50) # Import Font (Font file path , Font size)
    text_rect=text.render('Click Here',False,'Red') # Import Font text and surface (Text,Anti-alias,Colors)
    screen.blit(pygame.transform.scale(pygame.image.load("Picture/dqback3.png"), (1366 ,800)), (0, 0))
    screen.blit(exit, exit_rect)
    screen.blit(text_rect,(220 ,510))
    
    while running:
        Hello_world= Open_file()# Declare object class Open_file
        Hello_world.menu('Picture/Hello world.png',"Hello World\Hello World.bat",340,510) # Sent parameter (Logo image path , File open to path , rect x , rect y)
        if pygame.mouse.get_pressed()[0] and exit_rect.collidepoint(pygame.mouse.get_pos()):
            Main_menu() # Click "Exit" logo for back to Main menu
            running=False 

# Menu 1
def Main_menu():
    running=True
    click_me=pygame.image.load("Picture/Click Me.png") # Import "click_me" image file
    click_me_rect=click_me.get_rect(midbottom = (670 ,830)) # Image "click_me" rectangular (x,y)   
    screen.blit(pygame.transform.scale(pygame.image.load("Picture/dqback1.png"), (1366 ,800)), (0, 0)) # Import background image File on screen
    screen.blit(click_me,click_me_rect) # Import "Click me" logo on screen
    while running: # Operation loop      
        if pygame.mouse.get_pressed()[0] and click_me_rect.collidepoint(pygame.mouse.get_pos()):
            Sub_menu() # Go to Sub_menu Function
            running=False
        for event in pygame.event.get():           
               if event.type == pygame.QUIT or pygame.key.get_pressed()[K_ESCAPE]:
                   exit() # Setting press Esc to exit

        pygame.display.update() # Screen update image
        pygame.time.Clock().tick(60) # Screen FPS

#Screen Section
pygame.init() # Initialize pygame modules                         
screen = pygame.display.set_mode((1366 ,800)) # Screen size (Width , Length)
pygame.display.set_caption('User Interface By python') # Title bar 
programIcon = pygame.image.load('Picture/dq icon.png') # Title bar icon file import
pygame.display.set_icon(programIcon) # Title bar icon
Main_menu()# Go to Main_menu Function