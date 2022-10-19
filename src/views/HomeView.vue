<template>
  <div class="home">
    <div class="ui grid container">
      <div class="ui row">
        <div class="ten wide column">
          <img id = "drag1" class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img id = "drag2" class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img id = "drag3" class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img id = "drag4" class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img id = "drag5" class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img id = "drag6" class= "mt" alt="mt" src="../assets/mnt.jpeg">
        </div>
        <div class="six wide column">
          <HelloWorld msg="Welcome to Your Vue.js App"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  mounted () {
    // Make the DIV element draggable:
    dragElement(document.getElementById("drag1"));
    dragElement(document.getElementById("drag2"));
    dragElement(document.getElementById("drag3"));
    dragElement(document.getElementById("drag4"));
    dragElement(document.getElementById("drag5"));
    dragElement(document.getElementById("drag6"));

    function dragElement(elmnt) {
      var pos1 = 0, pos2 = 0, pos3 = 0, pos4 = 0;
      if (document.getElementById(elmnt.id + "header")) {
        // if present, the header is where you move the DIV from:
        document.getElementById(elmnt.id + "header").onmousedown = dragMouseDown;
      } else {
        // otherwise, move the DIV from anywhere inside the DIV:
        elmnt.onmousedown = dragMouseDown;
      }

      function dragMouseDown(e) {
        e = e || window.event;
        e.preventDefault();
        // get the mouse cursor position at startup:
        pos3 = e.clientX;
        pos4 = e.clientY;
        document.onmouseup = closeDragElement;
        // call a function whenever the cursor moves:
        document.onmousemove = elementDrag;
      }

      function elementDrag(e) {
        e = e || window.event;
        e.preventDefault();
        // calculate the new cursor position:
        pos1 = pos3 - e.clientX;
        pos2 = pos4 - e.clientY;
        pos3 = e.clientX;
        pos4 = e.clientY;
        // set the element's new position:
        elmnt.style.top = (elmnt.offsetTop - pos2) + "px";
        elmnt.style.left = (elmnt.offsetLeft - pos1) + "px";
      }

      function closeDragElement() {
        // stop moving when mouse button is released:
        document.onmouseup = null;
        document.onmousemove = null;
      }
    }
  }
}
</script>

<style type="text/css" scoped>
#drag1, #drag2, #drag3, #drag4, #drag5, #drag6 {
  position: absolute;
  z-index: 9;
  background-color: #f1f1f1;
  border: 1px solid #d3d3d3;
  text-align: center;
}

.mt {
  width: 28%;
  border-radius: 25px;
}

@media screen and (max-width: 600px) {
  .mt {
    width: 80%;
  }

  .mt:hover {
    width: 100%;
  }
}


@media screen and (min-width: 601px) and (max-width: 800px) {
  .mt {
    width: 45%;
  }

  .mt:hover {
    width: 50%;
  }
}



</style>
