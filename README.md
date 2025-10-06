```markdown
# IoT Agribusiness Platform

Este projeto é a continuação prática do TCC "Fatores e Aplicações Limitantes da IoT na Agricultura".  
Aqui transformamos pesquisa e teoria em um **sistema funcional** de agricultura digital.

---

## 🎯 Contexto (base no TCC)

Seu TCC identifica e descreve:  
- Os principais fatores limitantes para adoção de IoT em zonas rurais (conectividade, custos, capacitação).  
- Aplicações potenciais da IoT na agricultura: monitoramento de solo e ambiente, automação de irrigação, controle de insumos, integração de dados para tomada de decisão.  

Este repositório assume essa base teórica e inicia a construção prática do sistema.

---

## 🏗 Arquitetura proposta

```

[ Sensores / ESP32 ] → [ MQTT Broker ] → [ Backend / API ] → [ InfluxDB + Grafana ]
↘
→ [ Plataforma / Regras / Automação ]

````

Componentes:
- Dispositivos de borda (ESP32, sensores de solo/clima).  
- Broker MQTT (Mosquitto ou EMQX).  
- Backend (API REST / WebSocket).  
- Banco de séries temporais: InfluxDB.  
- Visualização / automação: Grafana, ThingsBoard, regras.

---

## 🚀 Roadmap / Fases de evolução

1. **Fase 0 – Protótipo local**  
   - Simulador de sensores publicando dados ao broker local.  
   - Docker Compose com Mosquitto, InfluxDB, Grafana.

2. **Fase 1 – Dispositivo real**  
   - Firmware ESP32 real conectando sensores e publicando MQTT.  
   - Integração com backend e dashboard.

3. **Fase 2 – Automação**  
   - Atuadores (válvulas, bombas) controlados via MQTT.  
   - Regras definidas (ex: ligar irrigação se umidade abaixo de limiar).

4. **Fase 3 – Expansão de escopo**  
   - Integração com drones / imagens / sensores remotos.  
   - Controle de insumos agrícolas (nutrientes, defensivos).  
   - Modelos preditivos (machine learning) para irrigação otimizada.

5. **Fase 4 – Validação em campo**  
   - Testes em fazendas reais.  
   - Coleta de falhas, métricas de desempenho.  
   - Ajustes e escalabilidade.

---

## 🧰 Como rodar (versão inicial via Docker)

Pré-requisitos:
- Docker  
- Docker Compose

```bash
git clone https://github.com/GustavoFelipe85/iot-agribusiness-tcc.git
cd iot-agribusiness-tcc
# (certifique-se de que o docker-compose.yml esteja em /infrastructure ou na raiz)
docker-compose up -d
````

Serviços esperados:

* Broker MQTT: `localhost:1883`
* InfluxDB: `http://localhost:8086`
* Grafana: `http://localhost:3000`

---

## 📂 Estrutura de diretórios recomendada

```
/infrastructure/        → docker-compose, arquivos de infraestrutura  
/firmware/              → código para ESP32 / sensores  
/backend/                → API, lógica de controle  
/dashboards/             → painéis exportados  
/docs/                   → capítulos do TCC, referências  
.gitignore
LICENSE
README.md
```

---

## 🛠️ Contribuição

* Abra uma *issue* antes de propor mudanças grandes.
* Siga o estilo de commits (mensagens claras).
* Submeta *pull requests* com testes e documentação.

---

## 📜 Licença

Este projeto está licenciado sob a [MIT License](./LICENSE).
Você é livre para usar, modificar, distribuir, desde que preserve o copyright e a licença.

---

```

---

Se quiser, posso já gerar um *commit patch* você aplicar no repositório (diff) com essas mudanças. Você prefere receber o patch/diff ou vou montar já os arquivos `docker-compose.yml`, `.gitignore` e estrutura para você subir?
::contentReference[oaicite:0]{index=0}
```

