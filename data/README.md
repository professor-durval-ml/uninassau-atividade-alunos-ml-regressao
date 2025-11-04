# Datasets Disponíveis para o Projeto

## 📊 Visão Geral

Estão disponíveis **10 datasets diferentes** para o projeto. Cada grupo deve **escolher apenas 1 dataset** para trabalhar ao longo de todas as 5 etapas.

**IMPORTANTE:** Todos os datasets foram criados com **problemas intencionais** (valores faltantes, outliers, inconsistências, duplicatas, etc.) para simular dados do mundo real.

---

## 🎯 Como Escolher o Dataset

### Critérios de Escolha
1. **Interesse do grupo** - Qual tema é mais interessante?
2. **Aplicabilidade** - Qual tem mais relevância prática?
3. **Complexidade** - Alguns têm mais variáveis categóricas/numéricas
4. **Originalidade** - Evite escolher o mesmo que outros grupos

### Distribuição Sugerida
- Comunique ao professor qual dataset escolheu na primeira semana

---

## 📁 Dataset 1: Desempenho Acadêmico de Estudantes

### 📄 Arquivo
`students_performance.csv`

### 🎯 Objetivo
Prever a **nota final** de estudantes universitários (0-100) com base em hábitos de estudo, condições socioeconômicas e características pessoais.

### 📊 Características
- **Registros:** 2.510
- **Features:** 13
- **Variável Alvo:** `final_grade` (0-100 pontos)
- **Tipo:** Regressão

### 📝 Variáveis

#### Demográficas
- `student_id`: ID único
- `age`: Idade (18-25 anos)
- `gender`: Gênero (M/F)
- `parental_education`: Educação dos pais (high_school, bachelor, master, doctorate)

#### Acadêmicas
- `study_hours_week`: Horas de estudo por semana
- `attendance_rate`: Taxa de frequência (%)
- `previous_scores`: Notas anteriores (0-100)
- `tutoring`: Recebe tutoria (Yes/No)
- `extracurricular`: Atividades extracurriculares (Yes/No)

#### Infraestrutura e Bem-estar
- `internet_quality`: Qualidade da internet (Poor/Good/Excellent)
- `family_income`: Renda familiar (Low/Medium/High)
- `sleep_hours`: Horas de sono por dia
- `health_status`: Estado de saúde (Poor/Good/Excellent)

### 💡 Aplicação Prática
Identificar estudantes em risco de baixo desempenho para implementar programas de apoio preventivo.

---

## 📁 Dataset 2: Vendas Mensais de E-commerce

### 📄 Arquivo
`ecommerce_sales.csv`

### 🎯 Objetivo
Prever **vendas mensais** (em R$) de uma loja online com base em métricas de marketing, tráfego e comportamento do consumidor.

### 📊 Características
- **Registros:** 2.510
- **Features:** 16
- **Variável Alvo:** `monthly_sales` (vendas em R$)
- **Tipo:** Regressão

### 📝 Variáveis

#### Marketing e Tráfego
- `sale_id`: ID único
- `marketing_spend`: Investimento em marketing (R$)
- `website_traffic`: Visitantes mensais
- `conversion_rate`: Taxa de conversão (%)
- `mobile_traffic_pct`: Porcentagem de tráfego mobile

#### Produto e Preço
- `num_products`: Número de produtos no catálogo
- `avg_price`: Preço médio dos produtos (R$)
- `discount_percentage`: Desconto médio oferecido (%)
- `product_category`: Categoria (Electronics, Fashion, Home, Books, Sports)

#### Experiência do Cliente
- `avg_product_rating`: Avaliação média (0-5)
- `customer_reviews`: Número de avaliações
- `return_rate`: Taxa de devolução (%)
- `free_shipping`: Frete grátis (Yes/No)
- `payment_methods`: Métodos de pagamento aceitos

#### Mercado
- `competition_level`: Nível de competição (Low/Medium/High)
- `seasonality`: Sazonalidade (Low/Medium/High)

### 💡 Aplicação Prática
Otimizar investimentos em marketing e estratégias de vendas para maximizar receita.

---

## 📁 Dataset 3: Consumo de Energia Residencial

### 📄 Arquivo
`energy_consumption.csv`

### 🎯 Objetivo
Prever **consumo mensal de energia** (kWh) de residências com base em características da casa e hábitos dos moradores.

### 📊 Características
- **Registros:** 2.510
- **Features:** 16
- **Variável Alvo:** `monthly_consumption_kwh` (consumo em kWh)
- **Tipo:** Regressão

### 📝 Variáveis

#### Características da Residência
- `house_id`: ID único
- `house_area_sqm`: Área construída (m²)
- `num_rooms`: Número de cômodos
- `house_age_years`: Idade da casa (anos)
- `insulation_quality`: Qualidade do isolamento (Poor/Average/Good)
- `energy_efficiency_rating`: Classificação energética (A-E)

#### Moradores e Uso
- `num_residents`: Número de moradores
- `num_appliances`: Número de eletrodomésticos
- `home_office_hours`: Horas de home office por dia

#### Sistemas e Equipamentos
- `air_conditioning`: Ar condicionado (None/1/2/3+)
- `heating_system`: Sistema de aquecimento (None/Electric/Gas/Solar)
- `solar_panels`: Painéis solares (Yes/No)
- `electric_car`: Carro elétrico (Yes/No)
- `smart_thermostat`: Termostato inteligente (Yes/No)

#### Ambiente
- `has_pool`: Piscina (Yes/No)
- `avg_temperature`: Temperatura média externa (°C)

### 💡 Aplicação Prática
Prever consumo para precificação dinâmica, identificar consumidores de alto consumo, recomendar melhorias de eficiência.

---

## 📁 Dataset 4: Preços de Imóveis

### 📄 Arquivo
`housing_prices.csv`

### 🎯 Objetivo
Prever **preço de venda** de imóveis (em R$) com base em características físicas, localização e infraestrutura.

### 📊 Características
- **Registros:** 2.510
- **Features:** 17
- **Variável Alvo:** `price_brl` (preço em R$)
- **Tipo:** Regressão

### 📝 Variáveis

#### Características Físicas
- `property_id`: ID único
- `built_area_sqm`: Área construída (m²)
- `bedrooms`: Número de quartos
- `bathrooms`: Número de banheiros
- `parking_spaces`: Vagas de garagem
- `num_rooms`: Total de cômodos
- `property_age_years`: Idade do imóvel (anos)
- `floor_number`: Andar (0 = térreo/casa)

#### Localização e Vista
- `location`: Localização (Centro, Zona Sul/Norte/Leste/Oeste, Subúrbio)
- `view_type`: Tipo de vista (None/City/Park/Sea)
- `nearby_metro_km`: Distância até metrô (km)

#### Infraestrutura e Amenidades
- `infrastructure`: Infraestrutura do condomínio (Básica/Completa/Premium)
- `condo_fee`: Taxa de condomínio (R$/mês)
- `has_security`: Segurança 24h (Yes/No)
- `has_pool`: Piscina (Yes/No)
- `has_elevator`: Elevador (Yes/No)

#### Outros
- `property_type`: Tipo (Apartamento/Casa/Cobertura)
- `furnished`: Mobiliado (Yes/No)

### 💡 Aplicação Prática
Precificação automática de imóveis, identificar oportunidades de investimento, avaliar tendências de mercado.

---

## 📁 Dataset 5: Tempo de Entrega de Pedidos

### 📄 Arquivo
`delivery_time.csv`

### 🎯 Objetivo
Prever **tempo de entrega** (em horas) de pedidos com base em logística, condições de tráfego e características do pedido.

### 📊 Características
- **Registros:** 2.510
- **Features:** 16
- **Variável Alvo:** `delivery_time_hours` (tempo em horas)
- **Tipo:** Regressão

### 📝 Variáveis

#### Características do Pedido
- `delivery_id`: ID único
- `distance_km`: Distância até destino (km)
- `package_weight_kg`: Peso do pacote (kg)
- `delivery_type`: Tipo (Express/Standard/Economy)
- `is_priority`: Prioridade (Yes/No)
- `package_fragile`: Frágil (Yes/No)

#### Logística
- `vehicle_type`: Veículo (Moto/Carro/Van/Caminhão)
- `driver_experience_years`: Experiência do entregador (anos)
- `num_stops`: Número de paradas na rota
- `delivery_zone`: Zona de entrega (Urbana/Suburbana/Rural)
- `fuel_cost`: Custo do combustível (R$/litro)

#### Condições Externas
- `traffic_condition`: Tráfego (Baixo/Médio/Alto/Congestionado)
- `weather`: Clima (Ensolarado/Nublado/Chuva Leve/Forte/Tempestade)
- `time_of_day`: Horário (Madrugada/Manhã/Tarde/Noite)
- `day_of_week`: Dia (Seg-Qui/Sexta/Sábado/Domingo)

#### Feedback
- `customer_rating`: Avaliação do cliente (0-5)

### 💡 Aplicação Prática
Otimizar rotas de entrega, prever atrasos, melhorar experiência do cliente, precificação dinâmica.

---

## 📁 Dataset 6: Salário de Profissionais de TI

### 📄 Arquivo
`salary_prediction.csv`

### 🎯 Objetivo
Prever **salário anual** (em R$) de profissionais de TI com base em experiência, formação, habilidades técnicas e características do emprego.

### 📊 Características
- **Registros:** 2.520
- **Features:** 17
- **Variável Alvo:** `annual_salary_brl` (salário anual em R$)
- **Tipo:** Regressão

### 📝 Variáveis

#### Experiência e Formação
- `professional_id`: ID único
- `years_experience`: Anos de experiência (0-20)
- `education_level`: Nível educacional (Técnico, Superior, Pós-graduação, Mestrado, Doutorado)
- `certifications`: Número de certificações (0-10)

#### Área e Cargo
- `area`: Área de atuação (Desenvolvimento, Dados, Segurança, DevOps, Gestão, Suporte)
- `seniority`: Senioridade (Júnior, Pleno, Sênior, Especialista, Gerente)
- `company_size`: Tamanho da empresa (Pequena, Média, Grande, Multinacional)

#### Habilidades Técnicas
- `programming_languages`: Linguagens de programação conhecidas (1-10)
- `frameworks_known`: Frameworks conhecidos (0-15)
- `github_contributions`: Contribuições no GitHub (0-500)

#### Localização e Regime
- `location`: Localização (Capital, Interior, Região Metropolitana)
- `work_mode`: Modo de trabalho (Presencial, Remoto, Híbrido)
- `hours_per_week`: Horas trabalhadas por semana (30-50)

#### Desenvolvimento Profissional
- `english_level`: Nível de inglês (Básico, Intermediário, Avançado, Fluente)
- `conferences_attended`: Conferências participadas (0-10)
- `projects_completed`: Projetos completados (5-200)

#### Benefícios
- `has_stock_options`: Stock options (Sim/Não)

### 💡 Aplicação Prática
Precificação justa de salários, planejamento de carreira, análise de tendências salariais no mercado de TI.

---

## 📁 Dataset 7: Visualizações de Vídeos no YouTube

### 📄 Arquivo
`youtube_views.csv`

### 🎯 Objetivo
Prever **número de visualizações** de vídeos no YouTube com base em características do vídeo, canal e estratégias de promoção.

### 📊 Características
- **Registros:** 2.520
- **Features:** 21
- **Variável Alvo:** `total_views` (visualizações totais)
- **Tipo:** Regressão

### 📝 Variáveis

#### Características do Vídeo
- `video_id`: ID único
- `duration_minutes`: Duração em minutos (2-60)
- `title_length`: Tamanho do título (10-100 caracteres)
- `description_length`: Tamanho da descrição (50-1000 caracteres)
- `tags_count`: Número de tags (0-50)
- `has_thumbnail_custom`: Thumbnail personalizada (Sim/Não)
- `video_quality`: Qualidade do vídeo (480p, 720p, 1080p, 4K)

#### Categoria e Conteúdo
- `category`: Categoria (Educação, Gaming, Música, Vlogs, Tecnologia, Culinária, Fitness)
- `language`: Idioma (Português, Inglês, Espanhol)
- `has_subtitles`: Legendas (Sim/Não)

#### Características do Canal
- `channel_subscribers`: Inscritos no canal (100-1.000.000)
- `channel_age_months`: Idade do canal em meses (1-120)
- `previous_videos_count`: Vídeos publicados anteriormente (0-500)
- `avg_upload_frequency_days`: Frequência de upload em dias (1-30)

#### Engajamento e Promoção
- `comments_count`: Número de comentários (0-10.000)
- `likes_count`: Número de likes (0-50.000)
- `shares_count`: Número de compartilhamentos (0-5.000)
- `playlist_adds`: Adições a playlists (0-1.000)
- `promoted`: Vídeo promovido (Sim/Não)

#### Timing
- `upload_time`: Horário de upload (Madrugada, Manhã, Tarde, Noite)
- `upload_day`: Dia de upload (Seg-Qui, Sexta, Sábado, Domingo)

### 💡 Aplicação Prática
Otimizar estratégias de conteúdo, prever performance de vídeos, definir melhores horários de publicação.

---

## 📁 Dataset 8: Avaliação de Restaurantes

### 📄 Arquivo
`restaurant_rating.csv`

### 🎯 Objetivo
Prever **nota média** (0-5 estrelas) de restaurantes com base em localização, qualidade, serviço e presença online.

### 📊 Características
- **Registros:** 2.520
- **Features:** 24
- **Variável Alvo:** `average_rating` (nota de 1.0 a 5.0)
- **Tipo:** Regressão

### 📝 Variáveis

#### Localização e Ambiente
- `restaurant_id`: ID único
- `location_type`: Tipo de localização (Centro, Bairro Nobre, Subúrbio, Periferia, Shopping)
- `neighborhood_safety`: Segurança do bairro (Baixa, Média, Alta)
- `parking_available`: Estacionamento (Sim/Não)
- `outdoor_seating`: Mesas ao ar livre (Sim/Não)

#### Características do Estabelecimento
- `cuisine_type`: Tipo de cozinha (Brasileira, Italiana, Japonesa, Americana, Árabe, Vegetariana)
- `price_range`: Faixa de preço (Econômico, Moderado, Caro, Muito Caro)
- `seating_capacity`: Capacidade de lugares (20-200)
- `years_in_business`: Anos em operação (0-30)

#### Serviço e Atendimento
- `waiters_count`: Número de garçons (2-20)
- `avg_service_time_min`: Tempo médio de atendimento em minutos (15-90)
- `accepts_reservations`: Aceita reservas (Sim/Não)
- `delivery_service`: Serviço de delivery (Sim/Não)

#### Qualidade e Higiene
- `health_inspection_score`: Pontuação de inspeção sanitária (50-100)
- `chef_experience_years`: Experiência do chef em anos (1-30)
- `menu_variety_items`: Variedade do cardápio em itens (10-150)
- `daily_specials`: Pratos do dia (Sim/Não)

#### Marketing e Presença Online
- `has_website`: Website próprio (Sim/Não)
- `social_media_followers`: Seguidores nas redes sociais (0-50.000)
- `instagram_posts_count`: Posts no Instagram (0-1.000)
- `online_reviews_count`: Número de avaliações online (5-2.000)

#### Diferenciais
- `live_music`: Música ao vivo (Sim/Não)
- `kids_friendly`: Ambiente para crianças (Sim/Não)
- `accepts_groups`: Aceita grupos (Sim/Não)

### 💡 Aplicação Prática
Identificar fatores que influenciam satisfação do cliente, melhorar serviços, otimizar marketing.

---

## 📁 Dataset 9: Preço de Carros Usados

### 📄 Arquivo
`used_cars_price.csv`

### 🎯 Objetivo
Prever **preço de revenda** (em R$) de carros usados com base em características do veículo, histórico e condição.

### 📊 Características
- **Registros:** 2.520
- **Features:** 25
- **Variável Alvo:** `price_brl` (preço em R$)
- **Tipo:** Regressão

### 📝 Variáveis

#### Características Básicas
- `car_id`: ID único
- `brand`: Marca (Toyota, Honda, Volkswagen, Chevrolet, Ford, Fiat, Hyundai)
- `model_year`: Ano do modelo (2010-2024)
- `mileage_km`: Quilometragem (5.000-250.000 km)
- `fuel_type`: Tipo de combustível (Gasolina, Etanol, Flex, Diesel, Híbrido, Elétrico)

#### Motor e Performance
- `engine_size_liters`: Tamanho do motor em litros (1.0-3.0)
- `horsepower`: Potência em cavalos (70-300)
- `transmission`: Transmissão (Manual, Automática, CVT, Automatizada)
- `drivetrain`: Tração (Dianteira, Traseira, 4x4)

#### Condição e Histórico
- `condition`: Condição geral (Excelente, Bom, Regular, Ruim)
- `previous_owners`: Donos anteriores (1-5)
- `accident_history`: Histórico de acidentes (Sem acidentes, 1 acidente leve, 2+ acidentes)
- `service_history`: Histórico de manutenção (Completo, Parcial, Sem histórico)

#### Features e Equipamentos
- `air_conditioning`: Ar condicionado (Sim/Não)
- `power_steering`: Direção hidráulica (Sim/Não)
- `power_windows`: Vidros elétricos (Sim/Não)
- `airbags_count`: Número de airbags (0-8)
- `abs_brakes`: Freios ABS (Sim/Não)

#### Acabamento e Extras
- `interior_material`: Material do interior (Tecido, Couro Sintético, Couro Legítimo)
- `sound_system`: Sistema de som (Básico, Premium, Multimídia)
- `sunroof`: Teto solar (Sim/Não)
- `parking_sensors`: Sensores de estacionamento (Sim/Não)

#### Documentação e Origem
- `warranty_months`: Garantia em meses (0-36)
- `imported`: Importado (Sim/Não)
- `color`: Cor (Prata, Preto, Branco, Vermelho, Azul, Cinza)

### 💡 Aplicação Prática
Precificação automática de veículos, avaliação de negociações, identificar boas oportunidades de compra.

---

## 📁 Dataset 10: Produtividade de Funcionários

### 📄 Arquivo
`employee_productivity.csv`

### 🎯 Objetivo
Prever **horas produtivas por semana** (0-40h) de funcionários com base em condições de trabalho, saúde e satisfação.

### 📊 Características
- **Registros:** 2.520
- **Features:** 28
- **Variável Alvo:** `productive_hours_week` (horas produtivas semanais)
- **Tipo:** Regressão

### 📝 Variáveis

#### Características Pessoais
- `employee_id`: ID único
- `age`: Idade (22-65 anos)
- `education_level`: Nível educacional (Ensino Médio, Superior Incompleto, Superior, Pós-graduação)
- `years_at_company`: Anos na empresa (0-20)
- `previous_experience_years`: Anos de experiência anterior (0-30)

#### Cargo e Departamento
- `department`: Departamento (TI, Vendas, Marketing, Operações, RH, Financeiro)
- `position_level`: Nível do cargo (Júnior, Pleno, Sênior, Coordenador, Gerente)
- `team_size`: Tamanho da equipe (3-30)
- `direct_reports`: Subordinados diretos (0-15)

#### Condições de Trabalho
- `commute_time_min`: Tempo de deslocamento em minutos (10-120)
- `work_mode`: Modo de trabalho (Presencial, Remoto, Híbrido)
- `workspace_quality`: Qualidade do espaço (Ruim, Adequado, Bom, Excelente)
- `noise_level`: Nível de ruído (Baixo, Moderado, Alto)

#### Ferramentas e Recursos
- `has_modern_equipment`: Equipamentos modernos (Sim/Não)
- `software_training_hours`: Horas de treinamento (0-100)
- `tools_satisfaction`: Satisfação com ferramentas (1-10)

#### Saúde e Bem-estar
- `sleep_hours_avg`: Horas médias de sono (4-10)
- `exercise_days_week`: Dias de exercício por semana (0-7)
- `stress_level`: Nível de estresse (Baixo, Moderado, Alto, Muito Alto)
- `sick_days_last_year`: Dias de doença no último ano (0-20)

#### Motivação e Engajamento
- `salary_satisfaction`: Satisfação salarial (1-10)
- `manager_quality`: Qualidade do gerente (1-10)
- `career_growth_score`: Pontuação de crescimento de carreira (1-10)
- `work_life_balance`: Equilíbrio trabalho-vida (1-10)

#### Suporte e Benefícios
- `has_flexible_hours`: Horário flexível (Sim/Não)
- `has_health_insurance`: Plano de saúde (Sim/Não)
- `has_meal_voucher`: Vale refeição (Sim/Não)
- `professional_development_budget`: Orçamento de desenvolvimento (R$ 0-10.000)

### 💡 Aplicação Prática
Identificar fatores que afetam produtividade, melhorar condições de trabalho, reduzir turnover.

---

## ⚠️ Problemas Comuns nos Datasets

Todos os datasets contêm os seguintes problemas **intencionais**:

| Problema | Quantidade Aproximada | Exemplos |
|----------|----------------------|----------|
| **Valores faltantes (NaN)** | ~8% dos dados | Células vazias em features numéricas e categóricas |
| **Outliers** | ~40-50 registros | Valores extremos mas não impossíveis |
| **Valores impossíveis** | ~10-20 registros | Idades negativas, ratings > 5, frequência > 100% |
| **Inconsistências** | ~10-15 registros | Baixo input mas alto output |
| **Duplicatas** | 10 registros | Registros muito similares com IDs diferentes |
| **Erros de digitação** | ~5-10 registros | Valores claramente errados |
| **Formatação** | ~70 registros | Espaços extras, MAIÚSCULAS, lowercase |

### Por que os dados têm problemas?

✅ **Realismo:** Dados do mundo real sempre têm problemas
✅ **Aprendizado:** Praticar limpeza e pré-processamento
✅ **Habilidades:** Desenvolver senso crítico sobre qualidade de dados

---

## 📊 Comparação dos Datasets

| # | Dataset | Dificuldade | Var. Categ. | Var. Num. | Correlações | Feature Eng. | Interpretab. |
|:-:|---------|:-----------:|:-----------:|:---------:|:-----------:|:------------:|:------------:|
| **1** | Estudantes | ⭐⭐ | 6 | 7 | Forte | Médio | Alta |
| **2** | E-commerce | ⭐⭐⭐ | 5 | 11 | Média | Alto | Média |
| **3** | Energia | ⭐⭐⭐ | 8 | 8 | Forte | Médio | Alta |
| **4** | Imóveis | ⭐⭐⭐⭐ | 8 | 9 | Forte | Alto | Alta |
| **5** | Entrega | ⭐⭐⭐ | 9 | 7 | Média | Alto | Média |
| **6** | Salário TI | ⭐⭐⭐ | 7 | 10 | Forte | Médio | Alta |
| **7** | YouTube | ⭐⭐⭐ | 8 | 13 | Média | Alto | Média |
| **8** | Restaurante | ⭐⭐ | 11 | 13 | Média | Médio | Alta |
| **9** | Carros Usados | ⭐⭐⭐ | 12 | 13 | Forte | Alto | Alta |
| **10** | Produtividade | ⭐⭐ | 12 | 16 | Média | Médio | Alta |

---

## 🚀 Como Começar

### 1. Escolha seu Dataset
Discuta com o grupo e escolha 1 dos 10 datasets disponíveis acima.

### 2. Leia as Instruções da Etapa 1
**Arquivo:** `etapas/etapa1/README.md`

Este arquivo contém:
- ✅ Todas as questões que você deve responder
- ✅ Análises obrigatórias
- ✅ Critérios de avaliação
- ✅ Dicas e orientações

### 3. Consulte a Documentação do Pandas
Você precisará aprender a usar pandas para trabalhar com os dados.

**Recursos oficiais:**
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [10 Minutes to Pandas](https://pandas.pydata.org/docs/user_guide/10min.html)
- [Pandas Cheat Sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)

**O que você vai precisar aprender:**
- Como carregar arquivos CSV
- Como visualizar dados (primeiras linhas, informações gerais)
- Como calcular estatísticas descritivas
- Como detectar valores faltantes

### 4. Explore e Aprenda
**Não há atalhos!** Você deve:
- 📖 Ler a documentação
- 🔍 Pesquisar como fazer cada tarefa
- 💡 Experimentar no Jupyter Notebook
- 🤝 Discutir com o grupo
- 🆘 Pedir ajuda ao professor quando travar

**Lembre-se:** O objetivo é APRENDER, não apenas copiar código pronto!

---

## 📞 Dúvidas Frequentes

**P: Posso mudar de dataset depois?**
R: Não recomendado, pois você perderá tempo. Escolha com cuidado!

**P: Posso combinar múltiplos datasets?**
R: Não. Use apenas 1 dataset.

**P: Os problemas nos dados são reais?**
R: Sim! Foram injetados propositalmente para simular dados do mundo real.

**P: Devo corrigir os problemas antes da Etapa 1?**
R: NÃO! A Etapa 1 é para identificar. A Etapa 2 é para corrigir.

**P: Qual dataset é mais fácil?**
R: "Estudantes" é o mais simples. "Imóveis" é o mais desafiador.

---

## 📚 Recursos Adicionais

- [Pandas Cheat Sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)
- [Data Cleaning Tutorial](https://www.kaggle.com/learn/data-cleaning)
- [EDA Guide](https://towardsdatascience.com/exploratory-data-analysis-8fc1cb20fd15)

---

**Boa escolha e bom trabalho!** 🎓

---

**Última atualização:** Janeiro 2025
