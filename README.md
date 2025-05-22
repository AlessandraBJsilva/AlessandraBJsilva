import pygame
import sys

# Inicializa o Pygame
pygame.init()

# Tamanho da Tela
largura = 500
altura = 500
tela = pygame.display.set_mode((largura, altura))
pygame.display.set_caption("Jogo Simples")

# Cores
branco = (255, 255, 255)
vermelho = (255, 0, 0)

# Posição Inicial do quadrado
x = 200
y = 200
velocidade = 5
tamanho = 50

# Loop do jogo
rodando = True
while rodando:
    pygame.time.delay(30)

    for evento in pygame.event.get():
        if evento.type == pygame.QUIT:
            rodando = False

    # Movimentação
    teclas = pygame.key.get_pressed()
    if teclas[pygame.K_LEFT]:
        x -= velocidade
    if teclas[pygame.K_RIGHT]:
        x += velocidade
    if teclas[pygame.K_UP]:
        y -= velocidade
    if teclas[pygame.K_DOWN]:
        y += velocidade

    # Atualiza tela
    tela.fill(branco)
    pygame.draw.rect(tela, vermelho, (x, y, tamanho, tamanho))
    pygame.display.update()

# Encerra o jogo
pygame.quit()
sys.exit()
