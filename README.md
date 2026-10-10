# Plano Crypto: compras por metas

Plano pessoal de compras de criptomoedas na Kraken Pro, com um aporte mensal fixo e compras por patamares do preço do BTC. Este repositório tem o site, que calcula quanto comprar em cada ativo. O bot que avisa dos patamares está num repositório privado.

**Site:** https://randreoliveira-hash.github.io/plano-crypto/

> Aviso: é um plano pessoal, não é aconselhamento financeiro. O bot só avisa. Cada compra e venda é feita pelo titular, na Kraken Pro.

## 1. Regras gerais

- **Aporte mensal:** 200 € no dia 1 de cada mês, de novembro de 2026 a outubro de 2027 (12 aportes). Vem do rendimento mensal.
- **Dinheiro parado:** o que não está investido fica reservado para os patamares de compra. Só entra no aporte mensal com a libertação (ver secção 3).
- **Metas:** o aporte é repartido pelos pesos abaixo. Os pesos são percentagens, não euros: o valor de cada compra depende do preço do momento.

| Ativo | Meta |
|---|---|
| BTC | 30% |
| ETH | 20% |
| SOL | 20% |
| LINK | 10% |
| AAVE | 10% |
| ARB | 10% |

- **Como se reparte o aporte:** o site reparte o aporte pelos desvios até às metas, por isso quem está mais abaixo da meta recebe mais. A soma é sempre igual ao aporte. Uma moeda acima da meta não recebe compra. O site nunca diz para vender.
- **Objetivo:** poucas transações e taxas baixas.

## 2. Patamares de compra (BTC)

Quando o BTC toca um patamar, o bot avisa. Compras tu na Kraken e marcas no bot, com `feito 68k` ou `saltar 68k`.

| Patamar (USD) | Quanto investir | Regra |
|---|---|---|
| 68.000 | 250 € | aviso ao tocar |
| 63.000 | 350 € | aviso ao tocar |
| 58.000 | 500 € | aviso ao tocar |
| 53.000 | o dinheiro parado que sobrar (máximo) | aviso ao tocar. A compra só se sugere depois de um fecho semanal acima de 63.000 USD |

- Um patamar marcado como **feito** deixa de avisar.
- Um patamar marcado como **saltar** devolve o valor ao dinheiro parado.
- O máximo espera pelo fecho semanal porque, em 2018 e em 2022, o primeiro toque em −57,5% do máximo foi seguido de novas quedas de 45% a 61%.

## 3. Libertação do dinheiro parado

- Se o BTC ficar acima de 87.000 USD durante 120 dias seguidos, a libertação fica ativa.
- Com a libertação ativa, no aporte do mês, se o BTC estiver acima de 87.000 USD nesse dia, o aporte sobe 100 €. Só acontece se houver dinheiro parado disponível.
- Se o BTC cair abaixo de 87.000 USD, a libertação pausa e o aporte volta a 200 €.
- Revisão do plano aos 6 meses (1 de maio de 2027).

## 4. Avisos de revisão

Estes avisos não compram nada. Pedem uma revisão do plano.

- BTC acima de 100.000 USD.
- Medo & Ganância de 20 ou menos (medo extremo), ou de 85 ou mais (ganância extrema).
- Cada aviso sai ao entrar na zona. Só volta a sair depois de 7 dias fora dela.
- Datas: 1 de dezembro de 2026 (primeiro mês), 1 de maio de 2027 (6 meses), 1 de novembro de 2027 (fim dos aportes).

## 5. Aporte mensal (dias 1 a 3)

- Nos dias 1, 2 e 3 de cada mês, às 09:00 UTC, o bot envia o aviso do aporte com ✅ Feito e ❌ Adiar.
- ✅ Feito fecha o mês.
- ❌ Adiar volta a avisar no dia seguinte, até ao dia 3.
- Sem resposta, o mês fica como "não feito" quando começa o seguinte.

## 6. Quando o bot avisa

Horas em UTC: na hora de verão em Portugal são 10h, e no inverno 9h.

| Quando | O que acontece |
|---|---|
| 09:00, todos os dias | aporte mensal, libertação, avisos de 100k e de Medo & Ganância, resumo de domingo, datas de revisão |
| 09:05, todos os dias | mensagem "VIGIA OK", para confirmar que a vigilância está ativa |
| a cada minuto | avisos dos patamares 68k, 63k e 58k, toque em 53k e fecho semanal do máximo (domingos, 23h–24h) |
| ao clicar em ✅ ou ❌, ou ao enviar um comando | o bot aplica e responde em 2 a 3 minutos |

Os avisos dos patamares chegam 1 a 2 minutos depois de o preço tocar o valor.

## 7. Comandos

- `feito 68k` e `saltar 68k` (também `63k` e `58k`)
- `feito max` e `saltar max`
- `estado`: mostra o preço, o F&G, o aporte do mês, os patamares, o máximo, o dinheiro parado estimado e a libertação
- Qualquer outro texto mostra a lista de comandos

## 8. O site

- **Preços:** Kraken, ao vivo. CoinGecko se a Kraken falhar.
- **A COMPRAR:** quantidade a comprar de cada moeda com o aporte do dia. Ao lado de cada moeda há um ícone para copiar essa quantidade (com vírgula e sem €), para colar na Kraken.
- **Topo:** Cripto, Fiat/Stable (euros e stablecoins, incluindo as que estão em Earn) e Total.
- **Atualização:** os saldos são lidos da Kraken de 30 em 30 minutos. "Auto 60s" atualiza os preços a cada 60 segundos. "Preço manual" serve para simular um preço; apagar o campo volta ao preço ao vivo.
- **Gravação:** guardar exige PIN. Os dados ficam numa base de dados privada, fora do site.
- **Chave da Kraken:** a que lê os saldos é só de leitura. Não permite comprar, vender nem levantar.

## 9. Notas

- O aporte do bot é fixo em 200 €. O campo "Aporte" do site não é lido pelo bot: se mudares o plano, muda nos dois sítios.
- Preços e saldos podem atrasar e diferem do preço de execução na Kraken.
- As metas, os patamares e as datas estão no código do bot (repositório privado).
