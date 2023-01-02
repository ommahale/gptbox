<script>
    import Speech from "$lib/shared/Speech.svelte"
    import SpeechSec from "$lib/shared/SpeechSec.svelte"
    import arrow from '$lib/assets/arrow.svg'
    import { fade } from 'svelte/transition';
    let data;
    async function handleClick(){
        let prompt= data
        let API_KEY="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"
//         axios.post("https://api.openai.com/v1/completions", {
//   prompt: prompt,
//   model: "davinci",
//   max_tokens: 1024
// }, {
//   headers: {
//     "Content-Type": "application/json",
//     "Authorization": `Bearer ${API_KEY}`
//   }
// })
//   .then(response => {
//     const generatedText = response.data.choices[0].text;
//     console.log(generatedText);
//   })
//   .catch(error => {
//     console.error(error);
//   });
let body= {
  "prompt": prompt,
  "model": "davincitext-davinci-003",
  "temprature":0,
  "max_tokens": 100
}
const response = await fetch("https://api.openai.com/v1/", {
    method: 'POST',
    headers: {
        "Content-Type": "application/json",
        "Authorization": `Bearer ${API_KEY}`
    },
    body: body
  });
  console.log(response)
        let newMessage={
            'isUser':true,
            'message':data
        }
        messagelog=[...messagelog, newMessage]
        data=""
    }
    let messagelog=[
        {
            "isUser":true,"message":"What is your name"
        },
        {
            "isUser":false,"message":"GPT-3"
        },
    ]
</script>
<body transition:fade>
    <div>
        <div class="pri" in:fade>
            <Speech>This is chat Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum eum, nesciunt veniam corrupti nulla nostrum? Nobis iure tempore ea pariatur!</Speech>
        </div>
        <div class="sec">
            <SpeechSec>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Autem tempora at nam optio earum laudantium id quo, quaerat perspiciatis iusto necessitatibus eos quia possimus nobis quasi ut sint a qui.</SpeechSec>
        </div>
        {#each messagelog as message}
            {#if message['isUser']}
                <div class="pri">
                    <Speech>{message['message']}</Speech>
                </div>
                
                {:else}
                <div class="sec">
                    <SpeechSec>{message['message']}</SpeechSec>
                </div>
            {/if}

        {/each}
    </div>
    <form >
        <input type="text" placeholder="Type your message here" bind:value={data}>
        <button type="submit" on:click={handleClick}><img src="{arrow}" alt="arrow"></button>
    </form>
</body>
<style>
    .pri{
        display: inline;
    }
    .sec{
        display: inline;
    }
    body{
        display: flex;
        justify-content: center;
        width: 100vw;
        height: 100vh;
        background-color: antiquewhite;
    }
    body div{
        width: 1100px;
        display: inline;
    }
    form{
        display: flex;
        justify-content: center;
        position: fixed;
        top: 90.6%;
        width: 100vw;
        padding: 20px;
        background-color: black;
    }
    input{
        border-radius: 30px;
        font-size: 1.1rem;
        padding: 5px;
        text-align: center;
        border: 0px;
        margin: 0 10px;
        width: 400px;
    }
    button:hover{

        background-color: rgb(48, 105, 105);

    }
    button{
        background-color: darkcyan;
        color: white;
        font-size: 1.1rem;
        border-radius: 50px;
        cursor: pointer;
        border: 0px;
    }
    img{
        max-height: 50px;
        
    }

</style>