<script>
    let gameContainer;
    
    import { onMount } from 'svelte';
    onMount(() => {
      // Cargar y mostrar el juego Phaser en el gameContainer
      const script = document.createElement('script');
      script.src = 'phaser-game.js'; // Ruta al archivo del juego Phaser
      gameContainer.appendChild(script);
    });

    let imageSources = ['/espacio.png', '/flechas.png'];

  </script>
  

  <div id="ctrls">
    {#each imageSources as src, i}
      <div class="ctrl" id="ctrl{i + 1}">
        <div class="imgdiv">
          <img {src} class="img" alt="" width="{i === 0 ? '230px' : '180px'}" height="{i === 0 ? '60px' : '180px'}" />
          <div class="accion">{i === 0 ? 'Atacar' : 'Movimiento'}</div>
        </div>
      </div>
    {/each}
  </div>
 
  <div id="game-container" bind:this={gameContainer}></div>

  <div id="ctrls">
    
  </div>
  
  <style>
    #ctrls{
      width: 100%;
      height: 500px;
      position: absolute;
      display: flex;
    }

    #ctrl1{
    color: white;
    width: 50%;
    height: 100%;
    display: flex; 
    justify-content: start; 
    align-items: center; 
  }

	#ctrl2{
    color: white;
    width: 50%;
    height: 100%;
    display: flex; 
    justify-content: end; 
    align-items: center; 
  }

  .imgdiv{
    width: 200px;
    height: 300px;
    margin-inline: 30px;
  }

  .img{
    margin-top: 80px;
    position: absolute;
  }

  .accion{
    height: 100%;
    color: white;
    font-size: xx-large;
    font-weight: bold;
    display: flex; 
    justify-content: center; 
    align-items: end; 
    position: relative;
  }

/*

  <div id="ctrls">
    {#each imageSources as src, i}
      <div class="ctrl" id="ctrl{i + 1}">
        <div class="imgdiv">
          <img {src} class="img" alt="" width="{i === 0 ? '230px' : '180px'}" height="{i === 0 ? '60px' : '180px'}" />
          <div class="accion">{i === 0 ? 'Atacar' : 'Movimiento'}</div>
        </div>
      </div>
    {/each}
  </div>

  #ctrls{
		width: 100%;
		height: 500px;
		position: absolute;
		display: flex;
    background-color: black;
	}

	#ctrl1{
    color: white;
    width: 50%;
    height: 100%;
    display: flex; 
    justify-content: start; 
    align-items: center; 
  }

	#ctrl2{
    color: white;
    width: 50%;
    height: 100%;
    display: flex; 
    justify-content: end; 
    align-items: center; 
  }

  .imgdiv{
    width: 200px;
    height: 300px;
    margin-inline: 30px;
  }

  .img{
    margin-top: 80px;
    position: absolute;
  }

  .accion{
    height: 100%;
    color: white;
    font-size: xx-large;
    font-weight: bold;
    display: flex; 
    justify-content: center; 
    align-items: end; 
    position: relative;
  }
*/

  </style>
  
  