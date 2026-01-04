# Análise de Tentativas de Login Suspeitas em Servidor Linux

## 1. Cenário
Durante a análise dos logs de autenticação de um servidor Linux, foram identificadas múltiplas tentativas de autenticação falhas via SSH em curto intervalo de tempo, direcionadas tanto a usuários inválidos quanto a usuários válidos do sistema.

## 2. Escopo
Esta análise tem como objetivo identificar padrões suspeitos a partir de eventos de autenticação falhos, avaliar o risco associado e propor ações iniciais de resposta, sem execução de medidas corretivas no ambiente analisado.

## 3. Evidências
As evidências foram coletadas a partir do arquivo de logs de autenticação do sistema (`/var/log/auth.log`).  
Foram observados os seguintes pontos relevantes:
- múltiplas entradas de `Failed password` associadas a um usuário inexistente;
- tentativas pontuais de autenticação falha direcionadas a um usuário legítimo;
- todas as tentativas originadas do mesmo endereço IP;
- ocorrência dos eventos em curto intervalo de tempo.

As evidências detalhadas encontram-se organizadas na pasta `/evidencias`.

## 4. Análise
A recorrência de falhas de autenticação para um usuário inexistente em curto intervalo de tempo é compatível com atividade de enumeração de usuários associada a tentativa de força bruta.

Observou-se que o nome do usuário inválido apresenta semelhança com o nome de um usuário legítimo do sistema, o que sugere a possibilidade de variações intencionais durante a tentativa de identificação de contas válidas. Esse comportamento é compatível com técnicas comuns utilizadas em fases iniciais de ataques de força bruta, nas quais o ator tenta inferir nomes de usuários válidos a partir de combinações semelhantes.

As tentativas direcionadas ao usuário legítimo ocorreram em menor volume, não caracterizando, isoladamente, um ataque persistente, mas reforçando a hipótese de enumeração prévia de contas.

Não foram identificadas evidências de autenticação bem-sucedida durante o período analisado.

## 5. Classificação do Incidente
- **Tipo:** Tentativa de acesso não autorizado  
- **Técnica observada:** Enumeração de usuários associada a força bruta  
- **Severidade:** Média  
- **Status:** Encerrado (ambiente de simulação)

## 6. Ação Recomendada
- Bloqueio temporário do endereço IP de origem;
- Revisão das políticas de autenticação e limite de tentativas;
- Monitoramento contínuo para eventos similares;
- Alerta ao time responsável em caso de recorrência.

## 7. Conclusão
O evento analisado foi classificado como tentativa de acesso não autorizado, sem impacto confirmado no ambiente. A análise evidencia a importância do monitoramento contínuo de logs de autenticação para identificação precoce de comportamentos suspeitos e possíveis tentativas de enumeração de usuários.
