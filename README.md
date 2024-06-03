# Automaces_para_empresa
#BackUp e atualização de planilhas
import pyautogui
import time
import subprocess
from datetime import date

# Tempo de espera para abertura de sites
tempo_abrir_sites = 10

# Pausa entre ações do pyautogui
pyautogui.PAUSE = 4

def abrir_navegador(url):
    """
    Abre o navegador Google Chrome e navega até a URL especificada.
    """
    subprocess.Popen(['start', 'chrome'], shell=True)
    time.sleep(tempo_abrir_sites)
    pyautogui.hotkey('ctrl', 'L')
    time.sleep(1)
    pyautogui.write(url)
    pyautogui.press('enter')
    time.sleep(tempo_abrir_sites)

def fechar_navegador():
    """
    Fecha o navegador usando a combinação de teclas Alt + F4.
    """
    pyautogui.hotkey('alt', 'f4')

def selecionar_data_padro(url):
    """
    Realiza operações na página 'Candidates', selecionando a data padrão.
    """
    try:
        abrir_navegador(url)
        
        # Selecionar a aba "Candidates"
        pyautogui.click(421, 134, duration=1)
        time.sleep(tempo_abrir_sites)

        # Remover filtros
        pyautogui.click(400, 384, duration=0.5)
        time.sleep(1)
        pyautogui.click(432, 382, duration=0.5)
        time.sleep(1)

        # Abrir a lista "profile details"
        pyautogui.click(265, 661, duration=1)

        # Descer a tela para centralizar
        pyautogui.scroll(-400)

        # Inserir a data padrão no campo "from"
        pyautogui.click(66, 808, duration=1)
        pyautogui.write("07/01/2022")

        # Subir a tela para centralizar
        pyautogui.scroll(400)

        # Solicitar envio do relatório por email
        pyautogui.click(1446, 331, duration=1)
        pyautogui.click(1353, 445, duration=1)
        pyautogui.click(1238, 640, duration=1)

    except Exception as e:
        print(f"Erro: {e}")
    finally:
        time.sleep(tempo_abrir_sites)
        fechar_navegador()

def pesquisar_requisicoes(url, search_text):
    """
    Realiza pesquisa de texto e manipulação de filtros na página 'Requisitions'.
    """
    try:
        abrir_navegador(url)

        # Abrir busca do navegador e digitar o texto a ser procurado
        pyautogui.hotkey('ctrl', 'f')
        time.sleep(1)
        pyautogui.write(search_text)
        time.sleep(2)
        pyautogui.press('enter')
        time.sleep(tempo_abrir_sites)

        # Clicar no resultado e aplicar filtros
        pyautogui.click(1204.25, 551.8, duration=1)
        time.sleep(tempo_abrir_sites)
        pyautogui.click(1828, 459, duration=1)
        pyautogui.click(1761, 574, duration=1)
        pyautogui.click(714, 395, duration=1)
        pyautogui.click(362, 480, duration=1)
        pyautogui.scroll(-200)
        pyautogui.click(1513, 872, duration=1)
        time.sleep(tempo_abrir_sites)

        # Inserir intervalo de datas
        pyautogui.click(385, 685, duration=1)
        pyautogui.click(295, 763, duration=1)
        pyautogui.click(125, 748, duration=1)
        pyautogui.write("01/01/2019")
        pyautogui.write("12/31/2024")
        pyautogui.click(430, 682, duration=1)
        pyautogui.click(1786, 812, duration=1)

        # Salvar e exportar relatório
        time.sleep(5)
        pyautogui.click(1446, 359, duration=1)
        pyautogui.click(880, 555, duration=1)
        data_hoje = date.today()
        data_formatada = data_hoje.strftime("[%d/%m/%Y]")
        pyautogui.write(data_formatada)
        pyautogui.click(1265, 656, duration=1)
        pyautogui.click(1794, 353, duration=1)

    except Exception as e:
        print(f"Erro: {e}")
    finally:
        time.sleep(tempo_abrir_sites * 10)
        fechar_navegador()

def detalhes_ofertas(url, search_text):
    """
    Realiza pesquisa de texto e manipulação de filtros na página 'Offer Details'.
    """
    try:
        abrir_navegador(url)

        # Abrir busca do navegador e digitar o texto a ser procurado
        pyautogui.hotkey('ctrl', 'f')
        time.sleep(1)
        pyautogui.write(search_text)
        time.sleep(2)
        pyautogui.press('enter')
        time.sleep(tempo_abrir_sites)

        # Clicar no resultado e aplicar filtros
        pyautogui.click(1117, 672, duration=1)
        pyautogui.click(1828, 459, duration=1)
        pyautogui.click(1761, 574, duration=1)
        pyautogui.click(727, 403, duration=1)
        pyautogui.click(357, 467, duration=1)
        pyautogui.scroll(-200)
        pyautogui.click(1513, 872, duration=1)
        time.sleep(2)

        # Inserir intervalo de datas e aplicar filtros
        pyautogui.click(385, 685, duration=1)
        pyautogui.click(387, 748, duration=1)
        pyautogui.scroll(500)
        pyautogui.click(295, 763, duration=1)
        pyautogui.click(125, 748, duration=1)
        pyautogui.write("01/01/2019")
        pyautogui.write("12/31/2024")
        pyautogui.click(430, 682, duration=1)
        pyautogui.click(642, 679, duration=1)
        pyautogui.click(1786, 812, duration=1)

        # Salvar e exportar relatório
        time.sleep(tempo_abrir_sites)
        pyautogui.click(1446, 359, duration=1)
        pyautogui.click(880, 555, duration=1)
        data_hoje = date.today()
        data_formatada = data_hoje.strftime("[%d/%m/%Y]")
        pyautogui.write(data_formatada)
        pyautogui.click(1258, 646, duration=1)
        pyautogui.click(1794, 353, duration=1)

    except Exception as e:
        print(f"Erro: {e}")
    finally:
        time.sleep(tempo_abrir_sites * 10)
        fechar_navegador()

def aberturas(url, search_text):
    """
    Realiza pesquisa de texto e manipulação de filtros na página 'Openings'.
    """
    try:
        abrir_navegador(url)

        # Abrir busca do navegador e digitar o texto a ser procurado
        pyautogui.hotkey('ctrl', 'f')
        time.sleep(1)
        pyautogui.write(search_text)
        time.sleep(2)
        pyautogui.press('enter')
        time.sleep(tempo_abrir_sites)

        # Clicar no resultado e aplicar filtros
        pyautogui.click(1112, 558, duration=1)
        pyautogui.click(1828, 459, duration=1)
        pyautogui.click(1758, 582, duration=1)
        pyautogui.click(727, 403, duration=1)
        pyautogui.click(357, 467, duration=1)
        pyautogui.scroll(-200)
        pyautogui.click(1513, 872, duration=1)
        time.sleep(2)

        # Inserir intervalo de datas e aplicar filtros
        pyautogui.click(385, 685, duration=1)
        pyautogui.click(387, 748, duration=1)
        pyautogui.scroll(900)
        pyautogui.click(295, 763, duration=1)
        pyautogui.click(125, 748, duration=1)
        pyautogui.write("01/01/2019")
        pyautogui.write("12/31/2024")
        pyautogui.click(1772, 817, duration=1)

        # Salvar e exportar relatório
        time.sleep(tempo_abrir_sites)
        pyautogui.click(1446, 359, duration=1)
        pyautogui.click(880, 555, duration=1)
        data_hoje = date.today()
        data_formatada = data_hoje.strftime("[%d/%m/%Y]")
        pyautogui.write(data_formatada)
        pyautogui.click(1258, 646, duration=1)
        pyautogui.click(1794, 353, duration=1)

    except Exception as e:
        print(f"Erro: {e}")
    finally:
        time.sleep(tempo_abrir_sites * 10)
        fechar_navegador()

# URLs e textos de pesquisa
url_cadidates = "https://company.hrhub.com/candidates"
url_requisitions = "https://company.hrhub.com/requisitions"
url_offer_details = "https://company.hrhub.com/offer-details"
url_openings = "https://company.hrhub.com/openings"
search_text = "Company Name"

# Execução das funções
selecionar_data_padro(url_cadidates)
pesquisar_requisicoes(url_requisitions, search_text)
detalhes_ofertas(url_offer_details, search_text)
aberturas(url_openings, search_text)
