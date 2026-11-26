📸 BurstAudit — Auditoria de Rajadas & EXIF (BETA)
O BurstAudit é uma ferramenta web gratuita e open-source criada para ajudar fotógrafos, editores e agências de eventos esportivos a identificar, auditar e isolar fotografias disparadas em rajada no mesmo segundo utilizando os metadados EXIF originais.
> 🚀 [**Acesse a ferramenta online aqui (GitHub Pages)**](https://lucascaraffini-pixel.github.io/contador-fotografias-esportivas)
>
> *(Não quer subir fotos agora? Clique em **"Carregar Demonstração"** no topo da página para testar com 2.500 fotos simuladas!)*
⚠️ Aviso de Versão BETA
Esta é a primeira versão pública BETA do BurstAudit. Ela foi liberada para que fotógrafos possam testar o fluxo em coberturas reais (esportes, eventos, casamentos, formaturas) e ajudar a identificar possíveis erros, incompatibilidades de câmeras ou oportunidades de melhoria.
Encontrou algum bug ou comportamento estranho? Abra uma Issue aqui — seu feedback é fundamental!
✨ Principais Recursos
⚡ Ultrarrápido (Leitura Parcial de 128 KB): Em vez de carregar imagens inteiras na memória, o motor lê apenas o cabeçalho EXIF (primeiros 128 KB) em segundo plano usando Web Workers. Permite auditar milhares de fotos em poucos segundos sem travar o navegador.
🔒 100% Local & Privado: Nenhuma foto é enviada para servidores ou nuvem. Todo o processamento acontece localmente no seu computador.
📷 Agrupamento Inteligente por Câmera: Lê as tags EXIF `Make` e `Model` para evitar falsos positivos quando duas ou mais câmeras diferentes fotografam o mesmo evento no mesmo segundo.
🎛️ Regras Configuráveis em Tempo Real: Ajuste o limite máximo de fotos/segundo (padrão: `10 f/s`), o peso da penalidade/pontuação e o agrupamento por câmera com recálculo instantâneo.
📊 Dashboard & Linha do Tempo: Cartões de KPI (Total Analisado, Taxa de Conformidade, Pico Máximo e Excedentes) e gráfico interativo destacando os segundos críticos.
🖼️ Miniaturas sob Demanda: Expanda qualquer segundo crítico na tabela e carregue as miniaturas apenas do grupo que deseja inspecionar, economizando memória RAM.
📦 Exportação & Isolamento de Excedentes:
CSV (formatado com BOM UTF-8 e `;` para abrir direto no Excel) e JSON para auditoria.
Scripts Automáticos (`.bat` para Windows e `.sh` para macOS/Linux) para mover os arquivos excedentes para a subpasta `Revisao_Excedentes`.
Movimentação Direta no Navegador: Move os arquivos automaticamente via File System Access API (compatível com Chrome e Edge).
🛠️ Como Usar
Acesse o link do BurstAudit no seu navegador (recomendado: Google Chrome ou Microsoft Edge).
Arraste uma pasta (ou clique em Selecionar Pasta Inteira / Selecionar Arquivos). Formatos suportados: `.JPG`, `.JPEG`, `.PNG` e `.WEBP`.
Aguarde a leitura dos metadados EXIF.
Ajuste o Limite Máximo (f/s) e a Penalidade conforme a regra do seu evento ou agência.
Inspecione os segundos críticos no gráfico e na tabela.
Escolha como deseja agir sobre os excedentes:
Baixe o relatório em CSV ou JSON.
Clique em Mover Diretamente (API Navegador) para isolar os arquivos excedentes na pasta `Revisao_Excedentes`.
Ou baixe o script `.bat` (Windows) / `.sh` (Mac/Linux), salve-o dentro da pasta das fotos e execute-o.
> **Nota sobre fotos sem EXIF:** Caso alguma imagem não possua data EXIF (`DateTimeOriginal`), o sistema utiliza automaticamente a data de modificação do arquivo como *fallback* e sinaliza visualmente na tabela.
🐛 Como Reportar Erros ou Sugerir Melhorias
Se você encontrar algum problema durante os testes da versão BETA, por favor abra uma Issue usando nosso modelo padronizado incluindo:
O que aconteceu (e o que você esperava que acontecesse).
Navegador e Sistema Operacional (ex.: Chrome no Windows 11, Safari no macOS).
Modelo da Câmera e formato do arquivo (ex.: Canon R6 Mark II, JPG direto da câmera ou exportado pelo Lightroom).
Quantidade aproximada de fotos no lote testado.
💻 Executando Localmente / Deploy
O projeto foi desenvolvido em arquivo único (`index.html`) sem necessidade de etapas de build ou instalação de dependências:
```bash
# Clone o repositório
git clone https://github.com/lucascaraffini-pixel/contador-fotografias-esportivas.git

# Abra o arquivo index.html diretamente no navegador
```
Para hospedar sua própria versão no GitHub Pages, basta ir em Settings → Pages, selecionar a branch `main` (pasta `/root`) e salvar.
📄 Licença
Este projeto está licenciado sob a licença MIT — veja o arquivo LICENSE para mais detalhes.
