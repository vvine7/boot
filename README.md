# boot
BOOTZAP
from distutils import text_file
import imp
from lib2to3.pgen2 import driver
from selenium import webdriver
import itertools
import time
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.common.keys import Keys #habilitando o teclado.

#Bot Versão 2.0 By Vinicius Daniel.

#Navegar até o whatsapp web
driver = webdriver.Chrome(ChromeDriverManager().install())
driver.get('https://web.whatsapp.com/') # pegar o link do Site.
time.sleep(28) #Tempo para scanear o celular no navegador.
# Definir Contatos e grupos e mensagem a ser enviada.
contatos = ['NOME DO CONTATO']
mensagem = ["TESTANDO BOOT ZAP 123..."]

def buscar_contato(contato):
    campo_pesquisa = driver.find_element_by_xpath('//div[contains(@class,"copyable-text selectable-text")]') #Pegar no campo de buscar contato.
    time.sleep(3)
    campo_pesquisa.click()
    campo_pesquisa.send_keys(contato)
    campo_pesquisa.send_keys(Keys.ENTER)

#Enviar mensagem
def enviar_mensagem(mensagem):
   campo_mensagem = driver.find_element_by_xpath('//div[contains(@class,"copyable-text selectable-text")]') #pegar no campo de enviar mensagem. 
   campo_mensagem [1].click()
   time.sleep(3)
   for text in itertools.repeat(campo_mensagem[1].send_keys(mensagem).50+1):
   campo_mensagem[1].send_keys(mensagem)# escrevendo a mensagem.
   campo_mensagem[1].send_keys(keys.ENTER)# apertando ENTER E ENVIANDO A MENSAGEM.
   

for contato in contatos:
    buscar_contato(contato)
    enviar_mensagem(mensagem)
# campo de pesquisa 'class="copyable-text selectable-text"
# campo de mensagem privada 'class="copyable-text selectable-text"
