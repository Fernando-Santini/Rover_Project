# Projeto: Rover de Inspeção: Robô Móvel para Monitoramento em Ambientes de Difícil Acesso

![Demonstração do Rover](https://www.youtube.com/watch?v=-yvNKuH8tJg)

Este repositório contém os materiais de **hardware** e **software** desenvolvidos para um rover de inspeção industrial com **câmera ESP32-CAM**, projetado para operar em **ambientes de alto risco**, onde a presença humana não é recomendada.  

---

## Visão Geral

O projeto consiste em uma **plataforma robótica de inspeção remota**, com **controle em tempo real** e **transmissão de vídeo**, equipada com múltiplos sensores para garantir **navegação segura** em ambientes industriais.  

### Funcionalidades:
-  Controle remoto via **interface web** (PC ou celular)  
-  Transmissão de vídeo em tempo real (ESP32-CAM com OV2640)  
-  Mira digital sobre o vídeo para inspeções de precisão  
-  Controle manual alternativo via **controle PS2 sem fio**  
-  Mecanismo de **pan/tilt** para movimentação da câmera  
-  Ajuste dinâmico de resolução e qualidade da transmissão  
-  Sistema de segurança com sensores ultrassônicos para **detecção de obstáculos e abismos**  

---

## 🛠 Hardware

### Componentes Principais
- **ESP32-CAM** com câmera **OV2640** (lente 66°) + **flat cable 200mm**  
- **Arduino Mega 2560** (controle central)  
- **Shield Moebius 4Motor&9Servo** (suporte a até 4 motores DC + 9 servomotores)  
- **Controle PS2 sem fio** + módulo receptor SPI  
- **Servomotor MG90S** (pan/tilt da câmera)  
- **4 x Motores DC JGB-520** com caixa de redução (330 RPM)  
- **6 x Sensores ultrassônicos HC-SR04** (detecção de obstáculos e abismos)  
- **Bateria LiPo 3s 30C – 11.1V 3300mAh**  
- (Opcional) **Módulo Wi-Fi de longo alcance**  

---

##  Arquitetura de Software

- **ESP32-CAM**  
  Responsável pela transmissão de vídeo em tempo real para a interface web  

- **Arduino Mega 2560**  
  Atua como **unidade de controle dos motores, servos e sensores**, recebendo comandos tanto da interface web (via ESP32 ou Raspberry, se usado como intermediário) quanto do controle PS2  

- **Controle PS2 sem fio**  
  Alternativa de controle manual, útil em testes locais ou redundância em campo  

- **Sensores HC-SR04**  
  Implementados nas laterais, frente e traseira, para garantir navegação segura e prevenção de colisões ou quedas  

---

##  Funcionalidades Implementadas

- **Navegação manual** via PS2 ou interface web  
- **Pan/Tilt da câmera** para inspeção detalhada de estruturas  
- **Prevenção de colisões**: bloqueio automático de movimento caso os sensores ultrassônicos detectem obstáculo dentro da distância mínima configurada  
- **Sistema redundante de comunicação** (PS2 + interface web)  
- **Mira digital** sobre a transmissão de vídeo para inspeção precisa  

---

##  Possíveis Aplicações

- Inspeção de **tubulações e estruturas metálicas** em fábricas  
- Navegação em **ambientes com risco elétrico ou químico**  
- Apoio em **manutenção preditiva** e **segurança industrial**  
- Base para **pesquisa acadêmica** em robótica móvel e visão computacional  

---

##  Planos Futuros

- Integração de sensores de distância **VL53L0X (infravermelho)** para maior precisão em ambientes internos  
- Implementação de **sensor de elevação** (ultrassônico voltado ao chão) para detectar quando o rover é levantado  
- Adição de **filtros na leitura da IMU** para controle mais estável  
- Suporte a **transmissão em primeira pessoa (FPV)** estilo drones/VR  
- Autonomia parcial com **algoritmos de evasão de obstáculos**  
