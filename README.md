# docker-node-express
Exemplo de node express rodando no docker

# Rodar servidor

```
npm start
```

# Gerar build a partir do Dockerfile
```
docker build -t docker-node-express .
```

# Rodar imagem
```
docker run -d -p 3000:3000 docker-node-express
```

# Usar docker compose para subir a imagem
```
docker-compose up
```

# Detalhes
Ao usar o docker-compose para subir o container, a aplicação estará escutando as alterações dos arquivos e caso atualize a página, as alterações serão mostradas. 
Porém isso funciona se rodar no WSL ou direto no linux. Caso execute no windows, as alterações não serão enviadas pro container portanto o nodemon não entenderá que
ocorreram mudanças, [veja aqui][1].

No meu caso, configurei para rodar o docker no WSL e desenvolvi a aplicação com VS Code.

Ao rodar o WSL, não é necessário instalar o VS Code dentro dele, dentro do WSL é possível executar o VS Code instalado no Windows instalando uma extensão o que é bem prático.

* Um detalhe que percebi, ao fazer as alterações no index.js, elas aparecerão no browser porém elas não serão refletidas na imagem.
Para que a imagem esteja atualizada, é preciso fazer o build novamente.

[1]: https://docs.docker.com/docker-for-windows/wsl/
