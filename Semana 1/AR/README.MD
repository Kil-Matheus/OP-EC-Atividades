# DOcumentação do Desenvolvimento em sala

## Resumo
Resumidamente, dentro do código HTML é importado 3 arquivos js, extensões para a utilização e renderização de obejtos em 2D/3D para o utilização da Realidade Virtual.

```javascript
    <script src="https://aframe.io/releases/1.3.0/aframe.min.js"></script>
    <script type='text/javascript' src='https://raw.githack.com/AR-js-org/AR.js/3.4.5/three.js/build/ar-threex-location-only.js'></script>
    <script type='text/javascript' src='https://raw.githack.com/AR-js-org/AR.js/3.4.5/aframe/build/aframe-ar.js'></script>
```

Após a importação das bibliotecas, é configurado um **assets**, uma tag que pode receber um objeto em 3D, uma imagem, um som ou um vídeo. Lá é feito as definições do objeto.

```javascript
    <a-assets> <!--Configuração de um assets-->>
        <audio id="som" preload="auto" src="beludo.mp3"></audio>
        <video id="kuka" src="beludo.mp4"></video>
        <img id="sete" src="../assets/001.png"/>
    </a-assets>
```

Depois é definido uma tag que renderiza o objeto na tela quando encontra o ponto de referência (hiro) e a segue até que o mesmo não se torne mais visível. Após tudo configurado, a linha de execução da câmera é inicializada.

```javascript
    <a-scene embedded arjs> <!--embedded: Permite que a cena AR seja renderizada como parte da página, sem ocupar a tela inteira.-->>
        <a-marker preset="hiro">
            <a-entity position="0 0 0" rotation="-90 0 0" scale="1 1 1" gltf-model="#shiba"></a-entity> <!--Adiciona um modelo 3D ao marcador-->
            <a-entity sound="src: #som; autoplay:true; loop:true"></a-entity> <!--Adiciona um som ao marcador-->
        </a-marker>

        <a-entity camera=""></a-entity>
    </a-scene>

```