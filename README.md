# Brindes Pulse

Dashboard independente de monitoramento do Gestão de Brindes.

## O que acompanha

- Saúde geral da aplicação;
- disponibilidade da sessão do painel;
- latência do endpoint público `/api/health`;
- estado da conexão com o banco;
- histórico de latência da sessão em gráfico;
- atualização automática a cada 30 segundos.

O dashboard consulta o endpoint público do sistema por caminho relativo. Em produção, o projeto deve ser publicado com um rewrite/proxy para o domínio do Gestão de Brindes ou servido no mesmo domínio. Nenhuma credencial é armazenada no navegador.

## Desenvolvimento local

```bash
python3 -m http.server 4173
```

Abra `http://localhost:4173`.

## Deploy

Projeto estático compatível com Vercel:

```bash
vercel --prod
```

## Segurança

O painel usa somente o endpoint público de saúde, que retorna status, versão, banco e horário. Não deve receber tokens, senhas ou cookies do sistema principal.
