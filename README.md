# Terminal de Ônibus da Beira: Sistema de Reservas (2026)

**Cadeira:** Programação Web | **Curso:** Engenharia Informática, 2.º ano
**Instituição:** Universidade Zambeze, Faculdade de Ciências e Tecnologia
**Docente:** MSc. Eng.º Félix Macueia
**Membros do grupo:** Augusto Botão, Paulo Augusto Nortamo

## 1. Descrição

Sistema de reservas para o terminal interprovincial da Beira, composto por duas partes:
um sistema web de administração (controlo de transportes, viagens, reservas e relatórios)
e um site público onde os clientes consultam partidas e fazem reservas virtuais.

## 2. Tecnologias

- Frontend: HTML, CSS e JavaScript
- Backend: PHP ou Node.js (Express)
- Base de dados: SQLite
- Controlo de versões: Git e GitHub

## 3. Entidades principais

Transporte (carro ligeiro, ônibus escolar, ônibus de passageiros), Viagem,
Terminal intermediário, Cliente, Reserva, Histórico de viagens.

## 4. Regras de negócio

### Carros ligeiros
- Capacidade máxima: 4 passageiros. Bagagem: menos de 20 kg.
- Transporte privado: preço = 10 MT x peso da carga (kg).
- Transporte do Estado: 20 MT por adulto e 10 MT por criança.

### Ônibus
- Número de assentos superior a 10.
- Escolar: gratuito. Assentos disponíveis = capacidade nominal - (2 x idade do ônibus em anos).
- Passageiros normais: 10 MT por adulto, gratuito para crianças.
- O estado do transporte afecta os lugares em pé.
  **Decisão do grupo:** (definir a regra, por exemplo: bom estado = X lugares em pé, mau estado = 0).

### Reservas
- A reserva online é virtual: garante o assento, mas só se efectiva no terminal físico.
- Cada reserva online reduz de imediato a capacidade disponível da viagem (sem overselling).
- Reservas podem ser de passageiros sozinhos ou acompanhados por menores.

## 5. Requisitos funcionais: administração

- Manter a lista de transportes disponíveis; ao partir, remover da lista e registar no histórico.
- Registar viagens: capacidade, destino, data e hora de partida, terminais intermediários, passageiros e reservas.
- Distribuir reservas pelos passageiros.
- Gerar relatórios no ecrã e guardar dados em ficheiro de texto.

## 6. Requisitos funcionais: site do cliente

- Informação geral: endereço do terminal, telefone, gerente e email, fotos do local.
- Tipos de transporte com destinos, capacidade e preço.
- Partidas de ônibus com capacidade, destino, data e hora, terminais intermediários.
- Cadastro do cliente: BI, nome, sexo, data de nascimento, endereço, telefone,
  local de trabalho ou estudo (se aplicável), foto.
- Reserva de bilhetes: escolha de partida, ônibus, destino, data e número de bilhetes.

## 7. Consultas e relatórios

1. Capacidade ocupada de uma viagem
2. Valor arrecadado por viagem
3. Destino mais vendido
4. Ônibus sem reservas
5. Média de lugares reservados
6. Ônibus totalmente reservados
7. Transporte com maior arrecadação histórica
