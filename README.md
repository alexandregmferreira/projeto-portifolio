# Projeto Portifólio Pessoal
### Projeto destinado a criação de uma pagina de apresentação de seus trabalhos e também a montagem da arquitetura na AWS.

## Entendendo o Projeto 
### 📁 <a href="website">website</a> onde estão os arquivos HTML e também as imagens.
#### 1- 🔧<b>Criamos primeiramente a Bucket e realizamos o upload dos arquivos</b>
#### 2- 🧱<b>Criamos o CloudFront</b>
<ul>
  <li>a- Clicamos em Create Distribution </li>
  <li>b- Escolhemos um nome e uma descrição "opcional" </li>
  <li>c- Escolhemos a opção S3 </li>
  <li>d- Em S3 Origin inserimos o link da Bucket localizado em permissões </li>
  <li>e- Em Origin Settings escolhemos as opções "Use recomended origin settings" </li>
  <li>f- Em cache Settings escolhemos as opções <ul>
    <li>a- Redirect HTTP to HTTPS </li>
    <li>b- Em Origin Request policy escolhemos a opção "AllViwerExceptHostHeader" </li>
    <li>c- Redirect HTTP to HTTPS </li>
    <ul> </li>
   <li>g- Em security escolhemos o WAF caso seja necessário e clicamos em create </li>
    </ul>    
#### 3- 🧩<b>AAgora vamos criar  função Lambda </b>
    <ul>
      <li>a- Clicamos em Create Function </li>
      <li>b- Escolhemos o nome e a descrição  </li>
      <li>c- Escolhemos o Runtime para Node </li>
      <li>d- Escolhemos as permissões básicas </li>
      <li>a- Clicamos em Create function 
      <ul>
        <li>a- Feito isso, acessamos a função lambda, clicamos em action no topo da tela e escolhemos a opção "deploy to Lambda@Edge"</li>
        <li>b- Escolhemos a opção "Configure new CloudFront trigger" </li>
        <li>c- Escolhemos a distribuição do CloudFront que criamos anteriormente </li>
        <li>d- Em Cache Behavior deixamos o "*" </li>
        <li>e- Em CloudFront Event deixamos o "Origin request" </li>
        <li>f- Confirme a replicação global e clique em "Deploy" </li>
      </ul>
      </li>
    </ul>
#### 4- Vamos criar o Application Load Balancer  

-
