<script>
    export default {
            data() {
                return {
                bgColor: '',
                textColor: 'white',
                showTxt: 'true',
                border: '8',
                txtArea: 'Cámbiame ;)',
                typography: '',
                opacity: '',
                size: ''

                }
            }
    }
</script>

<template>

<h2>Cambia la forma y propiedades del elemento</h2>
    <div class="container">
        <!-- Contenedor de los controladores -->
        <div class="subcontainer">
            <h4>Controladores 🎚️</h4>
            <form class="form">
                <!-- Selector de color del fondo -->
                <div>
                        <label for="title" class="form-label">Color de fondo</label>
                        <input type="text" v-model="bgColor" id="bgColor" class="form-control" placeholder="Escribe el nombre del color o código #hex">
                        <!-- <input type="color" v-model="bgColor" id="bgColor" class="form-control mt-1"> -->
                </div>
                <!-- Selector de color del txt -->
                <div>
                        <label for="txtColor" class="form-label">Color de texto</label>
                        <input type="text" v-model="textColor" id="txtColor" class="form-control" placeholder="Escribe el nombre del color o código #hex">
                        <!-- <input type="color" v-model="textColor" id="txtColor" class="form-control mt-1"> -->
                </div>
                <!-- Activador del texto -->
                <div class="form-check">
                    <input type="checkbox"  v-model="showTxt" id="showTxt" class="form-check-input" checked>
                    <label for="showTxt" class="form-check-label">Mostrar texto</label>
                </div>
                <!-- Selector range del border radius -->
                <div>
                    <label for="border" class="form-label">Borde</label>
                    <input type="range" v-model="border" class="form-range" id="border" value="0">
                </div>
                <!-- Contenido textual desde una text area -->
                <div>
                    <label for="txtArea" class="form-label">Texto</label>
                    <textarea v-model="txtArea" class="form-control" id="txtArea" rows="2"></textarea>
                </div> 
                <!-- Selector de tipografia -->
                <div>
                    <label for="typography" class="form-label">Tipografia</label>
                    <select type="select" v-model="typography" :style="{ fontFamily: `'Urbanist' + ${{typography}}` }" class="form-select" id="typography">
                        <option value="serif">Serif</option>
                        <option value="sans-serif">Sans serif</option>
                        <option value="monospace">Monospace</option>
                        <option value="cursive">Italic</option>
                    </select>
                </div>
                <!-- Activador de opacidad -->
                 <div class="form-check">
                    <label for="opacity" class="form-label">Opaco</label>
                    <input type="checkbox" v-model="opacity" class="form-check-input" id="opacity">
                 </div>
                 <!-- Selector de tamaño de fuente -->
                 <span>Tamaño del texto</span>
                 <div class="subform-row"> 
                    <div class="form-check">
                        <input type="radio" v-model="size" class="form-check-input" id="small" value="14"></input>    
                        <label for="size" class="form-check-label">Small</label>
                    </div>
                    <div class="form-check">
                        <input type="radio" v-model="size" class="form-check-input" id="medium" value="18"></input>    
                        <label for="size" class="form-check-label">Medium</label>
                    </div>
                    <div class="form-check">
                        <input type="radio" v-model="size" class="form-check-input" id="large" value="24"></input>    
                        <label for="size" class="form-check-label">Large</label>
                    </div>
                </div>
            </form>
        </div>
        <!-- Contenedor del objeto a renderizar -->
        <div class="object-dinamico" :style ="{ borderRadius: border + 'px', backgroundColor: bgColor, 'color': textColor, 'font-family': typography, 'font-size': size + 'px', opacity: opacity ? 0.5 : 1 }">
            <span v-show="showTxt" :style="{ fontSize: size + 'px' }" class="txt-dinamico">{{txtArea}} </span>
        </div>
    </div>


</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Urbanist:ital,wght@0,100..900;1,100..900&display=swap');

    .container {
        padding: 1rem;
        display: flex;
        flex-direction: row;
        justify-content: space-aroundy;
        align-items: start;
        gap: 2rem;
    }

    .subcontainer {
        display: flex;
        flex-direction: column;
        border: solid 2px black;
        width: 400px;
        border-radius: 8px;
        padding: 1rem;
        background-color: #D1E9F6;
    }

.subform-row {
    display: flex;
    flex-direction: row;
    gap: 1rem;
}

.form {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.object-dinamico {
    border: solid 2px white;
    outline: solid 2px black;
    height: 200px;
    width: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0px 319px 89px 0px rgba(0, 0, 0, 0.00), 0px 204px 82px 0px rgba(0, 0, 0, 0.01), 0px 115px 69px 0px rgba(0, 0, 0, 0.05), 0px 51px 51px 0px rgba(0, 0, 0, 0.09), 0px 13px 28px 0px rgba(0, 0, 0, 0.10);

}

.txt-dinamico {
    /* font-family: roboto, italic ; */
    display: inline-flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    font-size: 1.25rem;
    font-weight: 600;
    padding: 1rem;
}

h2 {
    color: aliceblue;
}

.subform-row {
    display: flex;
    flex-direction: row;
    gap: 1rem;
}

</style>