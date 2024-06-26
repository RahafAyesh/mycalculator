<script lang="ts">
    import Addtion from "$lib/icons/addtion.svelte";
    import Backspace from "$lib/icons/backspace.svelte";
import Division from "$lib/icons/division.svelte";
    import Equal from "$lib/icons/equal.svelte";
import Minus from "$lib/icons/minus.svelte";
    import Multiplication from "$lib/icons/multiplication.svelte";
import Squareroot from "$lib/icons/squareroot.svelte";

function addtoEquation (value:string ) {
equation+=value;
}

function backspace(){
  switch (equation.substring(equation.length-3,equation.length)){
case " * ":
case " - ":
case " + ":
case " / ":
equation= equation.substring(0,equation.length-3);
break;
default: equation= equation.substring(0,equation.length-1);
  }
 

 
}

function clear(){

    equation=("");

}
 
function result(){
equation=eval(equation);
}

let equation :string="";

</script>
<svelte:head>

<title>
    calculator
</title>

</svelte:head>

    <div  class="bg-white  rounded-3xl grid grid-cols-4  gap-1  p-6   font-semibold text-xl shadow-xl max-w-[16rem]"> 

        <div  class="bg-[#a2d2ff] rounded-xl col-span-4 min-h-12  flex items-center px-5 mb-2 text-white break-all ">
            

            {equation}


        </div>

 <button on:click={()=>addtoEquation("/100")} class="bg-[#f7d9e4] hover:bg-[#f2ccda]">%</button>
<button on:click={()=> backspace()} class="bg-[#f7d9e4]  hover:bg-[#f2ccda] ">
<Backspace/>

</button>
<button on:click= {clear} class="bg-[#f7d9e4]  hover:bg-[#f2ccda] ">C </button>
<button on:click= {()=>addtoEquation(' - ')} class="bg-[#b5d9f7] hover:bg-[#a8cfef] text-white"> <Minus/></button>
<button on:click={()=>addtoEquation('7')}>7</button>
<button on:click={()=>addtoEquation('8')}>8</button>
<button on:click={()=>addtoEquation('9')}>9</button>
<button  on:click={()=>addtoEquation(' / ')} class="bg-[#c1f1a5] hover:bg-[#b3eb95] text-white">
<Division/>
</button>
<button on:click={()=>addtoEquation('4')}>4</button>
<button on:click={()=>addtoEquation('5')}>5</button>
<button on:click={()=>addtoEquation('6')}>6</button>
<button  on:click={()=>addtoEquation(' * ')} class="bg-[#afe690] hover:bg-[#9dd27f] text-white"> 
    <Multiplication />
</button>
<button on:click={()=>addtoEquation('1')}>1</button>
<button on:click={() => addtoEquation('2')}>2</button>
<button on:click={() => addtoEquation('3')}>3</button>
<button on:click={() => addtoEquation(' + ')} class="bg-[#faaac7] hover:bg-[#ee9cba] text-white">
    <Addtion/>
</button>

<button on:click={()=>addtoEquation('.')}>.</button>
<button on:click={()=>addtoEquation('0')}>0</button>
<button on:click= {()=> result()} class="col-span-2 bg-[#ffc8dd] hover:bg-[#f0b7cd] ">
<Equal/>
</button>



    </div>

