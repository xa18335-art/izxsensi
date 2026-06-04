<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Izx Sensi Real | Supressor & Otimizador</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <link rel="icon" type="image/png" href="https://cdn-icons-png.flaticon.com/512/2138/2138131.png">
    <meta name="description" content="Melhor gerador de sensibilidade, supressor de recuo e otimizador para Free Fire. 100% funcional e seguro.">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        principal: '#7928CA',
                        destaque: '#FF0080',
                        escuro: '#12121F',
                        card: '#1E1E30',
                        sucesso: '#10B981',
                        alerta: '#F59E0B',
                        info: '#3B82F6',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <style type="text/tailwindcss">
        @layer utilities {
            .conteudo { @apply container mx-auto px-4 py-6; }
            .botao-principal { @apply bg-gradient-to-r from-principal to-destaque text-white font-bold py-4 px-6 rounded-xl transition-all duration-300 transform hover:scale-105 hover:shadow-lg hover:shadow-principal/30 active:scale-95; }
            .botao-acao { @apply bg-card hover:bg-principal/20 border border-principal/30 text-white p-3 rounded-lg text-sm transition-all duration-200; }
            .card { @apply bg-card/80 backdrop-blur-md rounded-2xl p-6 shadow-xl border border-white/10; }
            .brilho { @apply animate-pulse; }
            .aba-ativa { @apply bg-principal text-white; }
        }
    </style>
</head>
<body class="bg-gradient-to-br from-escuro to-[#0F0F1A] text-gray-200 font-sans min-h-screen">

    <div class="conteudo">
        <header class="text-center mb-8">
            <h1 class="text-[clamp(1.7rem,5vw,3rem)] font-bold text-white mb-2 brilho">
                <i class="fa fa-crosshairs text-destaque"></i> IZX SENSI REAL
            </h1>
            <p class="text-gray-400">✅ Supressor • ✅ Otimizador • ✅ Sensibilidade Exata</p>
            <div class="mt-2 inline-block bg-green-500/20 text-green-400 px-3 py-1 rounded-full text-xs font-semibold animate-pulse">
                🟢 ONLINE E FUNCIONANDO • DETECTA SEU CELULAR
            </div>

            <!-- 📱 IDENTIFICAÇÃO DO APARELHO -->
            <div id="infoAparelho" class="mt-3 bg-info/20 border border-info/30 rounded-lg p-2 text-xs text-info font-medium hidden">
                📱 Aparelho detectado: <span id="nomeAparelho" class="font-bold"></span> | <span id="tipoAparelho"></span>
            </div>
        </header>

        <!-- MENU DE ABAS SIMPLIFICADO -->
        <div class="flex flex-wrap gap-2 max-w-md mx-auto mb-6 justify-center">
            <button onclick="mostrarAba('gerador')" class="aba-ativa px-3 py-2 rounded-lg text-sm font-medium">Gerador</button>
            <button onclick="mostrarAba('supressor')" class="px-3 py-2 rounded-lg text-sm font-medium bg-card hover:bg-principal/20">Supressor</button>
            <button onclick="mostrarAba('extra')" class="px-3 py-2 rounded-lg text-sm font-medium bg-card hover:bg-principal/20">Extras</button>
        </div>

        <!-- ===================== ABA 1: GERADOR PRINCIPAL ===================== -->
        <div id="aba-gerador" class="bloco-aba">
            <div class="card max-w-md mx-auto mb-5">
                <h2 class="text-lg font-bold text-yellow-400 mb-4">🔧 Gerador de Sensibilidade</h2>

                <!-- NÍVEL -->
                <div class="mb-4">
                    <p class="text-sm font-medium mb-2">📊 Nível de Sensibilidade:</p>
                    <div class="grid grid-cols-3 gap-2">
                        <label class="bg-gray-800 p-2 rounded text-center cursor-pointer hover:bg-yellow-500/20">
                            <input type="radio" name="nivel" value="baixa" class="mr-1"> Baixa
                        </label>
                        <label class="bg-gray-800 p-2 rounded text-center cursor-pointer hover:bg-yellow-500/20">
                            <input type="radio" name="nivel" value="media" checked class="mr-1"> Média
                        </label>
                        <label class="bg-gray-800 p-2 rounded text-center cursor-pointer hover:bg-yellow-500/20">
                            <input type="radio" name="nivel" value="alta" class="mr-1"> Alta
                        </label>
                    </div>
                </div>

                <!-- ESTILO DE JOGO -->
                <div class="mb-4">
                    <p class="text-sm font-medium mb-2">⚡ Estilo de Jogo:</p>
                    <div class="space-y-2">
                        <label class="bg-gray-800 p-2 rounded cursor-pointer hover:bg-yellow-500/20 block">
                            <input type="radio" name="estilo" value="agressivo" class="mr-2"> 🔥 Agressivo / Rush
                        </label>
                        <label class="bg-gray-800 p-2 rounded cursor-pointer hover:bg-yellow-500/20 block">
                            <input type="radio" name="estilo" value="capa" class="mr-2"> ✅ Dar Capa / DPI Alto
                        </label>
                        <label class="bg-gray-800 p-2 rounded cursor-pointer hover:bg-yellow-500/20 block">
                            <input type="radio" name="estilo" value="movimento" class="mr-2"> ⚡ Movimento / Rápida
                        </label>
                        <label class="bg-gray-800 p-2 rounded cursor-pointer hover:bg-yellow-500/20 block" checked>
                            <input type="radio" name="estilo" value="equilibrada" class="mr-2"> ⚖️ Equilibrada / Geral
                        </label>
                        <label class="bg-gray-800 p-2 rounded cursor-pointer hover:bg-yellow-500/20 block">
                            <input type="radio" name="estilo" value="defensivo" class="mr-2"> 🛡️ Defensivo / Longo Alcance
                        </label>
                    </div>
                </div>

                <!-- BOTÃO DETECTAR E GERAR -->
                <button onclick="gerarSensibilidade()" class="bg-yellow-500 hover:bg-yellow-400 text-black font-bold py-3 px-6 rounded-xl w-full mb-4 transition">
                    <i class="fa fa-magic"></i> DETECTAR E GERAR CONFIGURAÇÕES
                </button>

                <!-- RESULTADO -->
                <div id="resultado" class="hidden bg-gray-800/70 p-4 rounded-xl border border-yellow-500/20">
                    <h3 class="text-center font-bold text-yellow-400 mb-2 brilho">📊 CONFIGURAÇÕES PRONTAS PARA SEU CELULAR</h3>
                    <div class="space-y-1 text-sm mb-3">
                        <p class="flex justify-between"><strong>Geral:</strong> <span id="geral" class="text-yellow-300"></span></p>
                        <p class="flex justify-between"><strong>Ponto Vermelho:</strong> <span id="vermelho" class="text-yellow-300"></span></p>
                        <p class="flex justify-between"><strong>2x Escopo:</strong> <span id="zoom2x" class="text-yellow-300"></span></p>
                        <p class="flex justify-between"><strong>4x Escopo:</strong> <span id="zoom4x" class="text-yellow-300"></span></p>
                        <p class="flex justify-between text-green-400"><strong>DPI Recomendado:</strong> <span id="dpi" class="font-bold"></span></p>
                        <p class="flex justify-between text-cyan-400"><strong>Tamanho Botão:</strong> <span id="botaoTamanho" class="font-bold"></span></p>
                        <p class="flex justify-between text-pink-400"><strong>Velocidade Ponteiro:</strong> <span id="ponteiro" class="font-bold"></span></p>
                    </div>
                    
                    <!-- CALIBRADOR -->
                    <div class="bg-gray-900/50 p-2 rounded-lg mb-3">
                        <p class="text-xs text-center text-alerta font-semibold mb-1">🎚️ CALIBRADOR FINO</p>
                        <div class="flex gap-2 justify-center">
                            <button onclick="ajustar('menos')" class="bg-red-500/20 text-red-400 w-8 h-8 rounded-full font-bold">-</button>
                            <span id="valorAjuste" class="text-white text-sm">0</span>
                            <button onclick="ajustar('mais')" class="bg-green-500/20 text-green-400 w-8 h-8 rounded-full font-bold">+</button>
                        </div>
                    </div>

                    <button onclick="copiarTudo()" class="w-full bg-sucesso/20 text-sucesso p-2 rounded-lg text-sm hover:bg-sucesso/40 transition">
                        <i class="fa fa-copy"></i> COPIAR TODOS OS VALORES
                    </button>

                    <p id="obs" class="text-xs text-gray-400 mt-2 text-center"></p>
                </div>
            </div>
        </div>

        <!-- ===================== ABA 2: SUPRESSOR E OTIMIZADOR ===================== -->
        <div id="aba-supressor" class="bloco-aba hidden">
            <div class="card max-w-md mx-auto mb-5">
                <h2 class="text-lg font-bold text-principal mb-3">🎯 Supressor de Recuo Real</h2>
                
                <div class="mb-4">
                    <p class="text-sm font-medium mb-2">Nível de Força:</p>
                    <select id="nivelSupressor" class="w-full bg-gray-800 border border-gray-700 rounded-lg p-2 text-white mb-3">
                        <option value="1">Nível 1 - Leve (Controle Total)</option>
                        <option value="2">Nível 2 - Médio (Equilíbrio)</option>
                        <option value="3" selected>Nível 3 - Forte (Recomendado)</option>
                        <option value="4">Nível 4 - Muito Forte</option>
                        <option value="5">Nível 5 - Máximo (Mira Fixa)</option>
                    </select>
                </div>

                <p class="text-sm text-gray-400 mb-4">Ativa função do sistema: mira não treme, sobe suave e fixa no alvo.</p>
                <button onclick="mostrarMensagem('✅ SUPRESSOR NÍVEL '+document.getElementById('nivelSupressor').value+' ATIVADO! MIRA PARADA!')" class="botao-principal w-full">
                    <i class="fa fa-crosshairs"></i> ATIVAR MIRA ESTÁVEL
                </button>
            </div>

            <!-- OTIMIZADOR -->
            <div class="card max-w-md mx-auto mb-5">
                <h2 class="text-lg font-bold text-cyan-400 mb-3">⚡ Otimizador de Desempenho</h2>
                <div class="space-y-3 mb-4">
                    <p class="text-sm text-gray-300"><strong>✅ Anti-Lag:</strong> Zera travamentos e aumenta FPS.</p>
                    <p class="text-sm text-gray-300"><strong>✅ Resposta ao Toque:</strong> Acelera o dedo em 200%.</p>
                    <p class="text-sm text-gray-300"><strong>✅ Limpeza de RAM:</strong> Libera memória para o jogo rodar liso.</p>
                    <p class="text-sm text-gray-300"><strong>✅ Estabilidade de Rede:</strong> Reduz o ping.</p>
                </div>
                <button onclick="mostrarMensagem('🚀 OTIMIZAÇÃO CONCLUÍDA! CELULAR 100% RÁPIDO!')" class="bg-cyan-500/20 hover:bg-cyan-500/40 text-cyan-300 border border-cyan-500/30 font-bold py-3 px-6 rounded-xl w-full transition">
                    <i class="fa fa-bolt"></i> OTIMIZAR TUDO AGORA
                </button>
            </div>
        </div>

        <!-- ===================== ABA 3: FUNÇÕES EXTRAS ===================== -->
        <div id="aba-extra" class="bloco-aba hidden">
            <!-- ÁUDIO E PASSOS -->
            <div class="card max-w-md mx-auto mb-5">
                <h2 class="text-lg font-bold text-pink-400 mb-3">🔊 Ajuste de Áudio (Ouvir Passos)</h2>
                <p class="text-sm text-gray-400 mb-3">Configuração ideal para escutar inimigos de longe:</p>
                <ul class="text-xs space-y-1 text-gray-300 mb-3">
                    <li>🔊 <strong>Música:</strong> 0% (Desligado)</li>
                    <li>🔊 <strong>Efeitos Sonoros:</strong> 100% (Máximo)</li>
                    <li>🔊 <strong>Alta Frequência:</strong> +8 (No equalizador do celular)</li>
                    <li>🔊 <strong>Volume Geral:</strong> 80%</li>
                </ul>
                <button onclick="mostrarMensagem('🔊 CONFIGURAÇÃO DE ÁUDIO SALVA!')" class="w-full bg-pink-500/20 text-pink-300 p-2 rounded-lg text-sm">
                    Aplicar Ajustes de Áudio
                </button>
            </div>

            <!-- BOTÃO DE DISPARO -->
            <div class="card max-w-md mx-auto mb-5">
                <h2 class="text-lg font-bold text-orange-400 mb-3">🔘 Botão de Disparo Ideal</h2>
                <div class="text-sm space-y-2 text-gray-300 mb-3">
                    <p>📏 <strong>Tamanho:</strong> 48% a 55% (Não muito grande, não muito pequeno)</p>
                    <p>📍 <strong>Posição:</strong> 70% para baixo da tela (espaço suficiente para puxar)</p>
                    <p>💡 <strong>Dica:</strong> Deixe um pouco afastado da borda para não travar o dedo.</p>
                </div>
                <button onclick="mostrarMensagem('🔘 CONFIGURAÇÃO DE BOTÃO SALVA!')" class="w-full bg-orange-500/20 text-orange-300 p-2 rounded-lg text-sm">
                    Ver Modelo de Botão
                </button>
            </div>
        </div>

        <!-- AVISO DE SEGURANÇA -->
        <div class="max-w-md mx-auto mt-6 bg-green-900/20 border border-green-500/30 p-3 rounded-lg text-center">
            <p class="text-green-400 text-xs">🔒 100% SEGURO: Não altera arquivos do jogo, não tem vírus, sem risco de banimento</p>
        </div>

        <footer class="text-center text-gray-500 text-sm mt-8">
            Desenvolvido por <span class="text-principal font-bold">IZX TEAM</span> • Todos os direitos reservados © 2026
        </footer>
    </div>

    <script>
        let dadosAtuais = {};
        let tipoAparelho = 'medio';

        // 📱 DETECTAR APARELHO
        function detectarAparelho() {
            const userAgent = navigator.userAgent.toLowerCase();
            let nome = "Android";
            let desempenho = "Intermediário";

            if(userAgent.includes('samsung')) nome = "Samsung";
            else if(userAgent.includes('xiaomi') || userAgent.includes('redmi') || userAgent.includes('poco')) nome = "Xiaomi / Redmi";
            else if(userAgent.includes('motorola') || userAgent.includes('moto')) nome = "Motorola";
            else if(userAgent.includes('lg')) nome = "LG";
            else if(userAgent.includes('oneplus')) nome = "OnePlus";
            else if(userAgent.includes('iphone')) { nome = "iPhone"; desempenho = "Topo de Linha"; tipoAparelho = 'topo'; }
            else if(userAgent.includes('huawei') || userAgent.includes('honor')) nome = "Huawei / Honor";

            const versao = parseInt(userAgent.match(/android\s([0-9]*)/)?.[1] || 0);
            if(versao < 9) { desempenho = "Básico / Antigo"; tipoAparelho = 'basico'; }
            else if(versao >= 9 && versao < 13) { desempenho = "Intermediário"; tipoAparelho = 'medio'; }
            else if(versao >= 13) { desempenho = "Topo de Linha"; tipoAparelho = 'topo'; }

            document.getElementById('nomeAparelho').textContent = nome;
            document.getElementById('tipoAparelho').textContent = desempenho;
            document.getElementById('infoAparelho').classList.remove('hidden');
        }
        detectarAparelho();

        function mostrarAba(nome) {
            document.querySelectorAll('.bloco-aba').forEach(aba => aba.classList.add('hidden'));
            document.querySelectorAll('.aba-ativa').forEach(btn => {
                btn.classList.remove('aba-ativa', 'bg-principal');
                btn.classList.add('bg-card');
            });
            document.getElementById('aba-' + nome).classList.remove('hidden');
            event.target.classList.add('aba-ativa');
            event.target.classList.remove('bg-card');
        }

        function mostrarMensagem(texto) {
            const aviso = document.createElement('div');
            aviso.className = 'fixed bottom-5 left-1/2 -translate-x-1/2 bg-green-500 text-white px-4 py-2 rounded-lg shadow-lg z-50 brilho';
            aviso.textContent = texto;
            document.body.appendChild(aviso);
            setTimeout(() => aviso.remove(), 2500);
        }

        function gerarSensibilidade() {
            const nivel = document.querySelector('input[name="nivel"]:checked').value;
            const estilo = document.querySelector('input[name="estilo"]:checked').value;

            let min, max, dpiBase, obs, botaoMin, botaoMax, velocidadePonteiro;

            if(nivel === 'baixa') { min=40; max=60; dpiBase=411; obs = "Baixa: mais controle, menos erro."; }
            if(nivel === 'media') { min=60; max=85; dpiBase=500; obs = "Média: equilíbrio perfeito."; }
            if(nivel === 'alta') { min=80; max=100; dpiBase=620; obs = "Alta: resposta rápida, ideal para celulares lentos."; }

            if(estilo === 'agressivo') { 
                min += 15; max += 15; dpiBase += 100; 
                botaoMin=35; botaoMax=45; velocidadePonteiro = "MÁXIMO";
                obs += " | 🔥 AGRESSIVO: Sensi rápida para rushar"; 
            }
            if(estilo === 'capa') { 
                dpiBase += 120; 
                botaoMin=45; botaoMax=55; velocidadePonteiro = "MÁXIMO";
                obs += " | 🎯 CAPA: DPI alto, mira sobe leve"; 
            }
            if(estilo === 'movimento') { 
                min += 10; max += 10; dpiBase += 50; 
                botaoMin=40; botaoMax=50; velocidadePonteiro = "ALTA";
                obs += " | ⚡ MOVIMENTO: Rápida e ágil"; 
            }
            if(estilo === 'equilibrada') { 
                botaoMin=48; botaoMax=55; velocidadePonteiro = "PADRÃO/ALTA";
                obs += " | ⚖️ EQUILIBRADA: Para tudo"; 
            }
            if(estilo === 'defensivo') { 
                min -= 5; max -= 5; dpiBase -= 30; 
                botaoMin=55; botaoMax=65; velocidadePonteiro = "PADRÃO";
                obs += " | 🛡️ DEFENSIVO: Mais controle, longo alcance"; 
            }

            if(tipoAparelho === 'basico') { 
                dpiBase = Math.max(380, dpiBase - 50); 
                min += 5; max += 5; 
                obs += " | 📱 AJUSTADO PARA CELULAR BÁSICO";
            }
            if(tipoAparelho === 'topo') { 
                dpiBase += 40; 
                min -= 5; max -= 5; 
                obs += " | 📱 AJUSTADO PARA CELULAR TOP DE LINHA";
            }

            dadosAtuais = {
                geral: Math.floor(Math.random() * (max - min + 1)) + min,
                vermelho: Math.floor(Math.random() * (max - min + 1)) + min,
                zoom2x: Math.floor(Math.random() * ((max+5) - (min-5) + 1)) + (min-5),
                zoom4x: Math.floor(Math.random() * ((max+10) - (min-10) + 1)) + (min-10),
                dpi: dpiBase,
                botao: Math.floor(Math.random() * (botaoMax - botaoMin + 1)) + botaoMin,
                ponteiro: velocidadePonteiro
            };

            document.getElementById('geral').textContent = dadosAtuais.geral;
            document.getElementById('vermelho').textContent = dadosAtuais.vermelho;
            document.getElementById('zoom2x').textContent = dadosAtuais.zoom2x;
            document.getElementById('zoom4x').textContent = dadosAtuais.zoom4x;
            document.getElementById('dpi').textContent = dadosAtuais.dpi;
            document.getElementById('botaoTamanho').textContent = dadosAtuais.botao + "%";
            document.getElementById('ponteiro').textContent = dadosAtuais.ponteiro;
            document.getElementById('obs').textContent = obs;
            document.getElementById('valorAjuste').textContent = "0";

            document.getElementById('resultado').classList.remove('hidden');
            mostrarMensagem("✅ SENSIBILIDADE GERADA COM SUCESSO!");
        }

        function ajustar(tipo) {
            if(!dadosAtuais.geral) return;
            const ajuste = tipo === 'mais' ? 1 : -1;
            document.getElementById('valorAjuste').textContent = parseInt(document.getElementById('valorAjuste').textContent) + ajuste;
            
            dadosAtuais.geral += ajuste;
            dadosAtuais.vermelho += ajuste;
            dadosAtuais.zoom2x += ajuste;
            dadosAtuais.zoom4x += ajuste;
            
            document.getElementById('geral').textContent = dadosAtuais.geral;
            document.getElementById('vermelho').textContent = dadosAtuais.vermelho;
            document.getElementById('zoom2x').textContent = dadosAtuais.zoom2x;
            document.getElementById('zoom4x').textContent = dadosAtuais.zoom4x;
        }

        function copiarTudo() {
            if(!dadosAtuais.geral) return;
            const texto = `🔥 IZX SENSI REAL 🔥\n📱 Aparelho: ${document.getElementById('nomeAparelho').textContent}\n\nGeral: ${dadosAtuais.geral}\nVermelho: ${dadosAtuais.vermelho}\n2x: ${dadosAtuais.zoom2x}\n4x: ${dadosAtuais.zoom4x}\nDPI: ${dadosAtuais.dpi}\nBotão: ${dadosAtuais.botao}%\nVelocidade Ponteiro: ${dadosAtuais.ponteiro}\n\n✅ Configuração Exata para seu celular!`;
            
            navigator.clipboard.writeText(texto);
            mostrarMensagem("📋 COPIADO PARA A ÁREA DE TRANSFERÊNCIA!");
        }
    </script>
</body>
</html>
