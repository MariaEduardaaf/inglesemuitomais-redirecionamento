# Redirecionamento do inglesemuitomais.com

Este repositório não é um site. É uma página só, cujo trabalho é mandar quem
digita **inglesemuitomais.com** (sem o `www`) para **www.inglesemuitomais.com**,
onde o site de verdade mora, no Cloudflare Pages.

## Por que isso existe

O domínio está registrado na Wix, e a Wix **não deixa trocar os nameservers**,
nem com o domínio desvinculado do site. Sem nameserver próprio, o Cloudflare
Pages só consegue atender o `www`, por CNAME. O domínio sem `www` precisaria de
um IP fixo, e o Pages não publica IP fixo.

O GitHub Pages publica. Então o domínio sem `www` aponta para os IPs do GitHub
Pages, cai aqui, e daqui é mandado para o endereço certo, levando junto o
caminho e a query.

## Isto é provisório

A solução definitiva é tirar o registro do domínio da Wix e levar para um
registrador que permita apontar os nameservers para o Cloudflare. Quando isso
acontecer, o domínio sem `www` passa a atender direto, e este repositório pode
ser apagado.

## Limitação conhecida

O redirecionamento é do lado do navegador (meta refresh + JavaScript), não um
301 do servidor. O GitHub Pages não faz redirecionamento de servidor. Para
quem acessa, é instantâneo e imperceptível. Para buscador, um 301 de verdade
seria melhor, e é mais um motivo para a transferência do domínio não ficar
para sempre na gaveta.
