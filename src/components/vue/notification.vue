<script setup>
    import {ref} from 'vue'
    let qty = ref(0)
    function add (){
        qty.value++
        console.log(qty)
    }
    function minus (){
        qty.value--
    }
    function restriccion(){
        if(qty.value>0){
        qty.value--
        }else{
            console.log('Ño')
        }
    }
    
</script>

<template>
    <div class="max-w-80 mx-auto bg-purple-300 rounded p-6">
        <div 
            v-if="qty > 0"
            class="bg-red-500 rounded-full text-white size-8 justify-center font-bold items-center flex"
            :class="{'bg-orange-500': qty > 3}"
            >
            
            {{ qty }}
        </div>
        <div v-else>
            Nadie te visita
        </div>
        <div class="flex">
            <div 
            @click="add" 
            class="bg-blue-800 text-white rounded items-center justify-center flex size-6 hover:cursor-pointer hover:text-green-400">
            +
        </div>
        <div 
            
            @click="restriccion" 
            class="bg-black text-white rounded items-center justify-center flex size-6 hover:cursor-pointer hover:text-green-400">
            -
        </div>
            
        </div>
        
        
       
    </div>
</template>