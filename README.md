# Chatbot_testes
# Chatbot_testes
import unittest
from datetime import datetime
from main import obter_resposta


class TestObterResposta(unittest.TestCase):

   def teste_saudacoes(self):
        self.assertEqual(obter_resposta("olá"), "Olá tudo bem!")
        self.assertEqual(obter_resposta("boa tarde"), "Olá tudo bem!")
        self.assertEqual(obter_resposta("bom dia"), "Olá tudo bem!")

  def teste_perguntas_simples(self):
        self.assertEqual(obter_resposta("como estás"), "Estou bem, obrigado!")
        self.assertEqual(obter_resposta("como te chamas"), "O meu nome é: Bot :)")
        self.assertEqual(obter_resposta("capital de portugal"), "Lisboa")
        self.assertEqual(obter_resposta("tempo"), "Está um dia de sol!")

  def teste_despedidas(self):
        self.assertEqual(obter_resposta("bye"), "Gostei de falar contigo! Até breve...")
        self.assertEqual(obter_resposta("adeus"), "Gostei de falar contigo! Até breve...")
        self.assertEqual(obter_resposta("tchau"), "Gostei de falar contigo! Até breve...")

  def teste_historia_portugal(self):
        self.assertEqual(obter_resposta("historia de portugal"), "Portugal tem uma rica história...")

  def teste_cozinhar(self):
        self.assertEqual(obter_resposta("cozinhar"), "Cozinhar é uma arte que envolve a preparação de alimentos...")

  def teste_programar(self):
        self.assertEqual(obter_resposta("sabes programar"), "Sim, posso ajudar com programação!")
        self.assertEqual(obter_resposta("programar"), "Programar é o processo de escrever código para criar software...")

  def teste_desenvolvimento(self):
        self.assertEqual(obter_resposta("desenvolvimento web"), "O desenvolvimento web envolve a criação de sites e aplicações web...")
        self.assertEqual(obter_resposta("desenvolvimento de software"), "O desenvolvimento de software é o processo de criar programas e aplicações...")
        self.assertEqual(obter_resposta("desenvolvimento de jogos"), "O desenvolvimento de jogos é a criação de jogos eletrônicos...")
        self.assertEqual(obter_resposta("desenvolvimento de aplicativos móveis"), "O desenvolvimento de aplicativos móveis é a criação de aplicativos para dispositivos móveis...")

  def teste_ia(self):
        self.assertEqual(obter_resposta("ia"), "A inteligência artificial é um campo da ciência da computação que se concentra na criação de sistemas que podem realizar tarefas que normalmente requerem inteligência humana.")
        self.assertEqual(obter_resposta("machine learning"), "O aprendizado de máquina é um subcampo da inteligência artificial que se concentra no desenvolvimento de algoritmos que permitem que os computadores aprendam com os dados.")
        self.assertEqual(obter_resposta("deep learning"), "O aprendizado profundo é uma subárea do aprendizado de máquina que utiliza redes neurais profundas para modelar dados complexos.")

  def teste_saude(self):
        self.assertEqual(obter_resposta("saúde"), "A saúde é um estado de completo bem-estar físico, mental e social, e não apenas a ausência de doenças ou enfermidades.")
        self.assertEqual(obter_resposta("problemas saúde"), "Problemas de saúde podem variar de leves a graves e podem afetar qualquer parte do corpo.")
        self.assertEqual(obter_resposta("sintomas"), "Sintomas são sinais ou indicações de uma condição médica ou doença.")

   def teste_indisposicao(self):
       self.assertEqual(obter_resposta("indisposição"), "Sintomas de indisposição podem incluir fadiga, dor de cabeça, náusea e outros sinais de que algo não está bem.")
        self.assertEqual(obter_resposta("sintomas de indisposição"), "Sintomas de indisposição podem incluir fadiga, dor de cabeça, náusea e outros sinais de que algo não está bem.")
        self.assertEqual(obter_resposta("estou com sintomas de indisposição"), "Sintomas de indisposição podem incluir fadiga, dor de cabeça, náusea e outros sinais de que algo não está bem.")

   def teste_horas_e_data(self):
        hora_atual = datetime.now().strftime("%H:%M")
        data_atual = datetime.now().strftime("%d-%m-%Y")
        self.assertTrue(obter_resposta("que horas são").startswith(f"São: {hora_atual[:4]}"))
        self.assertEqual(obter_resposta("qual é a data"), f"Hoje é dia: {data_atual}")

  def teste_resposta_padrao(self):
        self.assertEqual(obter_resposta("xyz123"), "Desculpa, não entendi a questão! xyz123")
        self.assertEqual(obter_resposta("teste123"), "Desculpa, não entendi a questão! teste123")


if __name__ == '__main__':
    unittest.main()
