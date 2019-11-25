<template>
    <div id="app" @mouseover="mouseOver">
        <transition-group name="fade-in" v-if="hovered" appear tag="div" class="parent-box" >
            <ChildBox v-for="(title,index) in titles" :item="title" :key="'child' + index" :index="index" />
        </transition-group>
    </div>
</template>
<script>
import ChildBox from './components/ChildBox.vue'

export default {
    name: 'app',
    data() {
        return {
            titles: [
                { text: 'Box-A', color: '#F9423A' },
                { text: 'Box-B', color: '#707372' },
                { text: 'Box-C', color: '#2CD5C4' }
            ],
            hovered: false
        }
    },
    components: {
        ChildBox
    },
    methods: {
        mouseOver() {
            this.hovered = true;
        }
    }
}
</script>
<style lang="scss">
#app{
  height:100vh
}
.fade-in-enter {
    opacity: 0;
    transform: scale(.5);
}

.fade-in-enter-active {
    transition: all .8s ease-in;
    transition-delay: calc(.2s * var(--i));
}

.parent-box {
    display: flex;
    width: 100%;
    justify-content: space-around;
    background: aliceblue;
    padding: 5%0;
}
</style>