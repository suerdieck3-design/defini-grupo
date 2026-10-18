# Redirecionador do grupo da estreia (Defini Cachos)

Página estática que fica na frente do link do grupo de WhatsApp. Serve para três coisas:
1. **Trocar de grupo em 1 minuto** quando o grupo atual lotar (1.024 pessoas), sem recriar anúncio.
2. **Disparar o pixel** Meta `1730433004715638` (PageView + Lead) e o GA4 `G-8T0GMFR8V8` (evento `whatsapp_click`). Com isso dá para montar público de quem clicou e, depois, otimizar por Lead.
3. **Separar a origem** pelo parâmetro `?o=`: `?o=fundo-frio`, `?o=fundo-quente`, `?o=contagem`, `?o=bio`.

## Como trocar o grupo
1. Abrir `index.html`, trocar o valor de `GRUPO` pelo link do grupo novo.
2. Publicar: `git commit` + `git push` no repositório GitHub `suerdieck3-design/defini-grupo` (GitHub Pages, entra no ar em 1 a 2 minutos). O link fica em base64 no HTML só para não ser raspado por robô no GitHub.
3. Testar num celular que não está no grupo: abrir a URL, conferir que cai no grupo certo.

## Regras
- Nunca colocar `chat.whatsapp.com` cru nos anúncios. Sempre a URL deste redirecionador.
- Trocar o alvo quando o grupo passar de **900** membros, não esperar lotar.
- O link da bio (linkcommerce) também deve apontar para cá, com `?o=bio`.
