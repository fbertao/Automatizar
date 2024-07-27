# Abrir o sistema da empresa
    # https://dlp.hashtagtreinamentos.com/python/intensivao/login
    # Abrir navegador
    # Entrar no site do sistema
# Fazer login
# Importar base de dados dos produtos
# Cadastrar um produto
# Repetir o processo 

# Abrir sistema da empresa
import pyautogui
import time
pyautogui.PAUSE = 0.5

pyautogui.press("win")
pyautogui.write("chrome")
pyautogui.press("enter")

pyautogui.write("https://dlp.hashtagtreinamentos.com/python/intensivao/login")
pyautogui.press("enter")
time.sleep(3)

# Posicionar o mouse 
# import pyautogui
# import time
# time.sleep(5)
# print(pyautogui.position())

# Fazer login
pyautogui.click(x=682, y=462)
pyautogui.write("projetopython@automatizar.com")

pyautogui.press("tab")
pyautogui.write("projetonum")

pyautogui.press("tab")
pyautogui.press("enter")
time.sleep(3)

# Importar bases de dados dos produtos
import pandas as pd
tabela = pd.read_csv("produtos.csv")
print(tabela)

# Cadastrar produto
for linha in tabela.index:
    pyautogui.click(x=653, y=294)
    codigo = tabela.loc[linha, "codigo"]
    pyautogui.write(str(codigo))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "marca"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "tipo"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "categoria"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "preco_unitario"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "custo"]))
    pyautogui.press("tab")
    obs = tabela.loc[linha, "obs"]
    if not pd.isna(obs):
        pyautogui.write(str(tabela.loc[linha, "obs"]))
    pyautogui.press("tab")
    pyautogui.press("enter")

pyautogui.scroll(5000)
