# Gerador de Assinatura de E-mail

Aplicação web estática para gerar e copiar assinaturas de e-mail da Secretaria Municipal de Cultura. Não há dependências, etapa de compilação ou servidor de aplicação.

## Como executar

Abra `gerador-assinatura-email.html` diretamente no navegador ou sirva a pasta pelo Apache/XAMPP:

```text
http://localhost/gerador-assinatura-email/gerador-assinatura-email.html
```

Preencha os dados, escolha a unidade e o cargo, clique em **Gerar assinatura** e depois em **Copiar assinatura**. A cópia preserva o HTML necessário para colar em um cliente de e-mail.

## Estrutura

```text
gerador-assinatura-email/
|-- assets/
|   |-- css/
|   |   `-- styles.css          # Aparência da página e responsividade
|   `-- images/
|       `-- background.png      # Imagem de fundo usada pelo CSS
|-- gerador-assinatura-email.html # Interface, dados e comportamento
`-- README.md
```

## Organização do CSS

O arquivo `assets/css/styles.css` está dividido nas seguintes seções:

- **Base:** normalização, tipografia e fundo da página.
- **Estrutura e marca:** cartão principal, logotipo e título.
- **Formulário e ações:** campos, estados de foco e botões.
- **Prévia da assinatura:** área de resultado e mensagem de cópia.
- **Responsividade:** ajustes para telas de até 520 px.

A imagem de fundo, antes incorporada ao CSS em Base64, fica em `assets/images/background.png`. Ao mover ou renomear esse arquivo, atualize o caminho relativo em `styles.css`.

## Manutenção

- Altere somente `assets/css/styles.css` para mudar a aparência da página.
- Os dados de locais e cargos permanecem nas constantes `locations` e `roles` dentro do HTML.
- Os estilos inline usados no HTML da assinatura gerada são intencionais. Muitos clientes de e-mail removem folhas de estilo externas, portanto esses estilos não devem ser transferidos para `styles.css`.
- As imagens da marca e da assinatura continuam incorporadas em Base64 no HTML para que a assinatura copiada seja autocontida.
- Preserve os IDs dos campos ao alterar a marcação, pois o JavaScript os utiliza para localizar os elementos.

## Compatibilidade

A funcionalidade de cópia usa a API moderna da área de transferência quando disponível e mantém um fallback para navegadores antigos. Em alguns navegadores, a API moderna exige que a página seja aberta por `localhost` ou HTTPS.
