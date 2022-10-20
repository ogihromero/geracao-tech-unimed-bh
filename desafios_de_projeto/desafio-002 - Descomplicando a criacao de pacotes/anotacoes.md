# Anotações - Descomplicando a criação de pacotes de processamento de imagens em Python

- **Módulos** servem como uma unidad organizacional de código que são carregados pelo compando import
- Enquanto isso, **Pacotes** são uma coleção de módulos com hierarquia
- A **modularização** favorece a legibilidade, manutenção e reaproveitamento do código
- **Pacotes** facilitam o compartilhamento e a instalação.
- `Pypi` é o repositório público ofical de Python
- `Wheel` e `Sdist` são tipos distruibções 
- `Setuptools` é um pacote usado para gerar as distrubuições e o `Twine` permite o upload delas no Pypi
- A criação de um `__init__.py` no diretório permite que ele seja invocado como módulo
- Se for um pacote com vários módulos, cada subdiretório de "submódulo" irá ter um `__init__.py` também.
- O `setup.py` é usado para especificar como o pacote deve ser construído.
- `requirements.txt` é usado para passar dependências que devem ser instaladas com o pacote, a especificação de versões é opcional.
- O Arquivo `README` é exibido na documentação na página do Pypi do pacote
- As distribuição será apenas um arquivo. Pode ser binária (`wheel`) ou de código-fonte (`sdist`), as versões mais recentes do `pip` só usam o código-fonte se necessário.
- É uma boa prática enviar as duas distruibções para o Pypi.