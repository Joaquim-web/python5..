# python5..
entregavel de pytho da semana 5
import re

def validar_email(email: str) -> bool:
    """Valida se o e-mail está no formato usuario@dominio.extensao"""
    padrao = r"^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"
    return bool(re.match(padrao, email))


def validar_cpf(cpf: str) -> bool:
    """Valida o formato do CPF: XXX.XXX.XXX-XX ou XXXXXXXXXXX (apenas dígitos)"""
    padrao = r"^(\d{3}\.\d{3}\.\d{3}-\d{2}|\d{11})$"
    return bool(re.match(padrao, cpf))


def validar_telefone(telefone: str) -> bool:
    """Valida o formato do telefone fixo ou celular com DDD: (XX) 9XXXX-XXXX ou (XX) XXXX-XXXX"""
    padrao = r"^\(\d{2}\)\s?9?\d{4}-\d{4}$"
    return bool(re.match(padrao, telefone))


def validar_data(data: str) -> bool:
    """Valida o formato de data: DD/MM/AAAA"""
    padrao = r"^(0[1-9]|[12][0-9]|3[01])/(0[1-9]|1[0-2])/\d{4}$"
    return bool(re.match(padrao, data))


# --- Teste das Funções Python ---
dados_teste = {
    "email": "usuario.exemplo@dominio.com.br",
    "cpf": "123.456.789-00",
    "telefone": "(11) 98765-4321",
    "data": "15/10/2026",
}

print("--- RESULTADOS VALIDAÇÃO PYTHON ---")
print(f"E-mail ({dados_teste['email']}): {validar_email(dados_teste['email'])}")
print(f"CPF ({dados_teste['cpf']}): {validar_cpf(dados_teste['cpf'])}")
print(f"Telefone ({dados_teste['telefone']}): {validar_telefone(dados_teste['telefone'])}")
print(f"Data ({dados_teste['data']}): {validar_data(dados_teste['data'])}\n")
