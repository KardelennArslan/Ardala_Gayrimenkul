<template>
  <div class="toggle-wrapper">
      <label class="toggle">
          <input 
            type="checkbox" 
            :checked="(darkTheme === 'dark-theme') ? true : false"
            @change="$emit('toggle')"
          />
          <span><i class="bx bx-moon"></i></span>
          <!-- <span class="toggler round"></span> -->
      </label>
  </div>
</template>

<script>
export default {
    props: ['darkTheme']
}
</script>

<style>
.toggle {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 26px;
}

.toggle input{
    opacity: 0;
    width: 0;
    height: 0;
}

.toggler{
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: var(--first-color);
    -webkit-transition: 0.4s;
    transition: 0.4s;
}

.toggler::before{
    position: absolute;
    content: "";
    height: 26px;
    width: 26px;
    left: 4px;
    right: 4px;
    background: #FFFFFF;
    -webkit-transition: 0.4s;
    transition: 0.4s;
}

input:checked + .toggler{
    background: #2196f3;
}

input:focus + .toggler{
    box-shadow: 0 0 2px #2196f3;
}

input:checked + .toggler::before{
    -webkit-transform: translateX(26px);
    -ms-transform: translateX(26px);
    transform: translateX(26px);
}

.toggler.round{
    border-radius: 34px;
}

.toggler.round::before{
    border-radius: 50%;
}
</style>