# Spam filtering (filtragem de informações indesejadas)

> 🌍 [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [Português](README.pt.md) · [Русский](README.ru.md)

Mantenha sua navegação limpa. O **Spam filtering** remove silenciosamente spam, pop-ups, banners, rastreadores e outros conteúdos indesejados das páginas que você visita — tudo roda localmente e de forma privada no seu dispositivo.

## Destaques

- Bloqueia spam e conteúdo indesejado: pop-ups, banners, rastreadores, scripts de análise
- Suas próprias regras em texto puro — importe, edite e exporte quando quiser
- Lista de permissões de sites confiáveis com um clique
- Estatísticas de bloqueio (hoje / total)
- Suporte a 10 idiomas
- 100% local e privado — sem conta, sem nuvem, sem coleta de dados
- Funciona no nível do sistema — não requer extensão de navegador

## Requisitos

- Windows 10 / 11

## Começando

1. Baixe o instalador mais recente na página de Releases.
2. Instale e inicie o aplicativo.
3. Ative **Assumir o proxy do sistema** nas Configurações.
4. Navegue normalmente — o conteúdo indesejado é filtrado automaticamente.

## Editando regras

As regras são armazenadas em texto puro, uma regra por linha. Adicione regras na página **Regras** do aplicativo ou importe um arquivo de regras.

### Formatos de regra

| Exemplo | Significado |
| --- | --- |
| `\|\|example.com^` | Bloquear um domínio e todos os seus subdomínios |
| `\|\|example.com/path/page^` | Bloquear um endereço específico (domínio + caminho) |
| `example.com` | Bloquear qualquer endereço que contenha este texto |
| `@@\|\|good.example.com^` | Exceção — sempre permitir este domínio |
| `0.0.0.0 ad.example.com` | Entrada no formato hosts |
| `! comentário` / `# comentário` | Linhas de comentário — linhas que começam com estes caracteres são ignoradas |

### Dicas

- `||` ancora a regra ao início do domínio; `^` significa "fim do domínio ou do caminho" (um separador).
- Comece simples: `||domínio^` cobre a maioria dos casos. Adicione regras de caminho apenas quando necessário, ex.: `||www.example.com/ads/banner^`.
- Depois de salvar uma regra, verifique as estatísticas de bloqueio para confirmar que ela funciona.

### Sobre HTTPS

Por padrão, as solicitações HTTPS são comparadas apenas pelo **nome do domínio** (o endereço completo é criptografado e não pode ser visto). Para comparar pelo **endereço completo, incluindo o caminho**, ative **Descriptografia HTTPS (MITM)** nas Configurações, instale o certificado raiz quando solicitado (apenas uma vez) e reinicie o navegador. Depois disso, regras de caminho como `||www.example.com/ads/banner^` também funcionam em sites HTTPS.

## Como funciona (resumo)

- O aplicativo executa um proxy local e pode assumir o proxy do sistema, de modo que o tráfego do navegador passa por ele.
- Cada solicitação é verificada contra suas regras: as correspondências são bloqueadas, todo o resto é encaminhado sem alterações.
- Toda a filtragem acontece no seu dispositivo — nada é enviado a lugar nenhum.

## Solução de problemas

**Sem acesso à internet?** A causa mais provável: o aplicativo foi fechado inesperadamente e deixou o proxy do sistema apontando para uma porta inválida.

- **Solução 1 — reinicie o aplicativo.** Ele detecta e limpa automaticamente as configurações de proxy residuais na inicialização.
- **Solução 2 — desative o proxy manualmente.** Configurações do Windows → Rede e Internet → Proxy → desative "Usar um servidor proxy".
- Normalmente, sair do aplicativo (ícone da bandeja → Sair) restaura o proxy automaticamente. Resíduos só ocorrem após saídas anormais (falha, encerramento forçado, queda de energia).

## Privacidade

O Spam filtering é uma ferramenta local. Toda a filtragem acontece no seu dispositivo — seus dados de navegação nunca saem do seu computador.

## Apoie este projeto

Se o Spam filtering ajuda você, considere apoiar o desenvolvimento futuro:

![Donate](donate.jpg)

## Licença

Todos os direitos reservados. Este software **não é open source**. Redistribuição e modificação não são permitidas sem autorização escrita explícita.
