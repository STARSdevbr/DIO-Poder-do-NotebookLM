# 📊 Relatório de Evidências e Troubleshooting

Este documento detalha os testes práticos realizados no NotebookLM para validar a adaptação de normativas da LGPD para servidores públicos.

## 1. O Ponto de Partida: A Barreira do Juridiquês
Inicialmente, o caderno foi criado com um resumo genérico [`00-Estudo de Caso - LGPD e ANPD - NotebookLM.png`](/evidencias/00-Estudo%20de%20Caso%20-%20LGPD%20e%20ANPD%20-%20NotebookLM.png). 
* **Prompt Testado ([`01-pergunta_base.png`](/evidencias/1-cicatriz/01-pergunta_base.png)):** *"Explique as atribuições do encarregado conforme os documentos"*
* **Resultado ([`02-resposta_fria.pdf`](/evidencias/1-cicatriz/02-resposta_fria.pdf)):** A IA gerou uma resposta estritamente técnica e fria.
* **Diagnóstico:** O texto era frio, denso e desmotivador para servidores sem formação jurídica, soando mais como uma auditoria do que como um apoio.

## 2. A Intervenção: Ajuste de Contexto (System Prompt)
O resumo do NotebookLM foi alterado para incluir diretrizes de empatia e foco em eficiência (demonstrados em [`03-configuracao_caderno.png`](/evidencias/2-ajuste/03-configuracao_caderno.png) e [`04-configuracao_caderno.pdf`](/evidencias/2-ajuste/04-configuracao_caderno.pdf)).
* **Diretriz injetada:** Foi explicitado que o público-alvo sofria da "Síndrome da Sobrecarga", não recebia remuneração extra pela função e que a IA deveria atuar para provar que a conformidade "resguarda o servidor, não sendo um fardo burocrático".

## 3. A "Cicatriz" Descoberta: O Viés de Ancoragem Documental
Ao repetir o prompt inicial, a resposta ([`05-mesma_pergunta_repetida.png`](/evidencias/3-resultado/05-mesma_pergunta_repetida.png)) permaneceu literal. Descobriu-se que a IA prioriza a exatidão do PDF em perguntas de definição ("O que é").
* **Resultado ([`06-resposta_empatica.pdf`](/evidencias/3-resultado/06-resposta_empatica.pdf)):** A IA manteve praticamente a mesma estrutura formal e fria da primeira tentativa.
* **Troubleshooting (A grande lição do projeto):** Descobriu-se que, em modelos RAG (Retrieval-Augmented Generation) como o NotebookLM, o compromisso primário da IA é com a fidelidade às fontes. Quando a pergunta exige uma **definição estrita** ("O que é? / Explique a lei"), a IA prioriza a exatidão jurídica do PDF, ignorando as diretrizes de empatia do System Prompt.

## 4. A Prova de Fogo: Comportamento vs. Definição
Para contornar isso, o prompt foi alterado para uma **ação comportamental**.
* **Novo Prompt ([`07-novo_prompt.png`](/evidencias/3-resultado/07-novo_prompt.png))**: Criação de um roteiro para o Microsoft Engage.
* **Resultado Alcançado ([`08-resultado-alcancado.pdf`](/evidencias/3-resultado/08-resultado-alcancado.pdf))**: Êxito total. A IA focou na proteção do servidor e na ajuda técnica.

## 🎯 Conclusão do Estudo de Caso
A verdadeira Engenharia de Prompts na gestão pública não depende apenas de fornecer as fontes corretas, mas sim da combinação de dois fatores fundamentais demonstrados neste estudo:
1. **Curadoria Inteligente:** O uso estratégico de regulamentações simplificadas (como o Guia Segurança da informação para ATPP) para viabilizar a conformidade em ambientes de alta carga operacional.
2. **Prompts de Ação:** A transição de consultas de definição ("o que é") para comandos comportamentais ("crie um roteiro/checklist"), quebrando a barreira do juridiquês e gerando valor imediato para o servidor.

---
*Desafio Acelere sua Aprendizagem com IA: Explore o Poder do NotebookLM*