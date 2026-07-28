# Streaming: Como Funciona:

O streaming é a tecnologia que permite **transmitir e reproduzir conteúdo multimédia (vídeo ou áudio) em tempo real**, sem que seja necessário descarregar o ficheiro completo antes de o começar a ver ou ouvir. Em vez de esperar por um único ficheiro gigante, o conteúdo chega ao dispositivo em pequenos pedaços que vão sendo reproduzidos assim que são recebidos.

![image](https://files.tecnoblog.net/wp-content/uploads/2025/06/tbr-streamings-1536x864.png)
---

## 1. O Conceito Base:

Em vez de transferir um ficheiro inteiro, o streaming <cite index="8-1,9-1">divide o conteúdo em pequenos segmentos ou "chunks", cada um deles podendo ser reproduzido de forma independente graças a uma frame-chave (keyframe) no início de cada segmento, que pode ser descodificada sem depender dos segmentos anteriores ou seguintes</cite>.

Este é o motivo pelo qual conseguimos:
- Começar a ver um vídeo quase de imediato (sem esperar o download completo)
- "Saltar" para diferentes pontos do vídeo
- Adaptar a qualidade da imagem em tempo real, consoante a velocidade da ligação

---

## 2. Codec vs. Protocolo — Não é a Mesma Coisa:

É comum confundir-se estes dois conceitos, mas são etapas distintas do processo:

> <cite index="1-1">Um codec, como o H.264 ou o H.265, trata da compressão — determina como os dados de vídeo e áudio são reduzidos para um tamanho manejável. Um protocolo trata do transporte — determina como esses dados comprimidos viajam de um ponto a outro</cite>.

Uma boa analogia:
> <cite index="1-1">Os codecs "viajam" dentro dos protocolos, tal como a carga viaja dentro de um camião</cite>.

**Codecs mais usados:**
- **H.264** — o mais difundido, equilíbrio entre compressão e compatibilidade
- **H.265 (HEVC)** — <cite index="3-1">mais recente e mais escolhido pela qualidade final que oferece mesmo com larguras de banda reduzidas</cite>

---

## 3. As Duas "Pernas" do Processo de Streaming:

Todo o fluxo de trabalho de transmissão em direto tem, geralmente, duas fases distintas:

1. **Ingest (primeira milha)** — <cite index="1-1">o vídeo é enviado de uma câmara/codificador para um servidor de streaming</cite>
2. **Distribuição (última milha)** — <cite index="1-1">o vídeo é enviado do servidor para os dispositivos dos espectadores</cite>

Alguns protocolos, como o **SRT**, conseguem <cite index="1-1">funcionar tanto na contribuição como na distribuição, dependendo da configuração</cite>. Já o **WebRTC** <cite index="1-1">lida com ambas as fases, sendo sobretudo utilizado em streaming interativo e cenários ponto-a-ponto</cite>.

---

## 4. TCP vs. UDP: A Base do Transporte:

<cite index="4-1">Por trás de cada protocolo de streaming existe um método de transporte — a forma como os pacotes de vídeo viajam pela internet. As duas opções principais são o TCP e o UDP</cite>.

- **TCP (Transmission Control Protocol):** <cite index="4-1">focado na fiabilidade — garante que todos os pacotes chegam e reenvia os que se perdem. É por isso que o HLS e o MPEG-DASH, protocolos baseados em HTTP, dependem do TCP</cite>.
- **UDP:** prioriza a velocidade em detrimento da garantia de entrega — ideal para comunicação quase instantânea, como videochamadas.

---

## 5. Principais Protocolos de Streaming:

| Protocolo | Uso típico | Características |
|---|---|---|
| **HLS** (HTTP Live Streaming) | Distribuição, streaming adaptativo | Baseado em HTTP, amplamente suportado (Apple) |
| **MPEG-DASH** | Distribuição, streaming adaptativo | <cite index="2-1">protocolo open-source usado por plataformas como YouTube e Netflix, agnóstico ao dispositivo e com suporte robusto a DRM</cite> |
| **WebRTC** | Comunicação em tempo real | <cite index="2-1">concebido para streaming de latência ultrabaixa, ideal para aplicações interativas como jogos, videoconferência e leilões ao vivo — funciona diretamente no browser sem plugins</cite> |
| **RTMP** | Ingest (contribuição) | <cite index="7-1">entrega vídeo a um ritmo semelhante a uma transmissão por cabo, em pouco mais de cinco segundos de atraso</cite> |
| **RTSP/RTP** | Vigilância, câmaras IP | <cite index="7-1">ainda mais rápido, com cerca de dois segundos de atraso</cite>; <cite index="5-1">continua a ser o padrão em sistemas de videovigilância, já que a maioria das câmaras IP ainda o suporta</cite> |
| **SRT** | Contribuição e distribuição | Robusto em redes instáveis, cada vez mais usado em broadcast profissional |

Vale notar que, apesar de rápidos, <cite index="7-1">o RTMP e o RTSP não são nativamente suportados pela maioria dos dispositivos finais (browsers, telemóveis, televisores), pelo que hoje são usados principalmente entre uma câmara/codificador e um servidor de media</cite>. Por isso, <cite index="7-1">muitos broadcasters transportam a transmissão em direto para o servidor usando um protocolo com estado como o RTMP e, a partir daí, convertem-na para uma tecnologia baseada em HTTP para distribuição multi-dispositivo</cite>.

---

## 6. O Papel do Bitrate Adaptativo (ABR):

Os protocolos modernos baseados em HTTP (HLS, DASH) permitem o **streaming de bitrate adaptativo**: o mesmo vídeo é codificado em várias qualidades (por exemplo, 360p, 720p, 1080p, 4K), e o dispositivo do espectador vai escolhendo automaticamente a versão mais adequada à sua ligação em cada momento — é por isso que a imagem por vezes "baixa de qualidade" momentaneamente em vez de parar de vez (buffering).

---

## 7. O Percurso Completo de uma Stream:

De forma resumida, uma transmissão passa pelas seguintes etapas:

1. **Captura** — câmara ou fonte gera o vídeo/áudio em bruto
2. **Codificação (encoding)** — o codec comprime os dados
3. **Ingest** — o stream é enviado para um servidor via protocolo de contribuição (ex: RTMP, SRT)
4. **Processamento no servidor** — transcodificação em múltiplas qualidades, empacotamento em segmentos
5. **Distribuição via CDN** — os segmentos são replicados por servidores próximos dos utilizadores para reduzir latência
6. <cite index="2-1">**Transmissão** — os pacotes de dados viajam via protocolos de streaming pela internet</cite>
7. <cite index="2-1">**Buffering** — o dispositivo do cliente armazena temporariamente os dados recebidos</cite>
8. <cite index="2-1">**Descodificação** — o dispositivo converte os dados comprimidos de volta em conteúdo visualizável</cite>
9. <cite index="2-1">**Reprodução** — o vídeo é exibido no ecrã</cite>

---

## 8. Breve Nota Histórica:

<cite index="3-1">Nos anos 90 surgiram alguns dos protocolos mais populares, como o Flash, o RTMP e o RTSP, e entre 2001 e 2010 o Adobe Flash manteve-se muito popular na maioria dos browsers</cite>. Com o tempo, esses protocolos proprietários foram sendo substituídos por soluções abertas e baseadas em HTTP (HLS, DASH), mais compatíveis com firewalls, proxies e dispositivos modernos.

---

## Fontes:

- [Video Streaming Protocols Explained — Castr](https://castr.com/blog/video-streaming-protocols-everything-you-need-to-know/)
- [Video Streaming Guide — Wowza](https://www.wowza.com/blog/video-streaming)
- [What are Video Streaming Protocols & How Do They Work? — VPlayed](https://www.vplayed.com/blog/video-streaming-protocols/)
- [Video Streaming Protocols: A Comprehensive Guide (2026) — VdoCipher](https://www.vdocipher.com/blog/video-streaming-protocols/)
- [Video Streaming Protocols: A Comprehensive Guide — Teyuto](https://teyuto.com/blog/what-are-streaming-protocols-how-do-they-work)
- [Streaming Protocols for Live Broadcasting — Dacast](https://www.dacast.com/blog/streaming-protocols/)
- [Streaming Protocols: Everything You Need to Know (Update) — Wowza](https://www.wowza.com/blog/streaming-protocols)
