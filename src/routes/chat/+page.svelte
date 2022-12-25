<script>
    import Speech from "$lib/shared/Speech.svelte"
    import SpeechSec from "$lib/shared/SpeechSec.svelte"
</script>
<div class="inner">
    <div>
        <div class="pri">
            <Speech>This is chat Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum eum, nesciunt veniam corrupti nulla nostrum? Nobis iure tempore ea pariatur!</Speech>
        </div>
        <div class="sec">
            <SpeechSec>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quis, omnis reiciendis accusantium praesentium at tempora nihil aliquam ipsum minima repellendus repudiandae quibusdam? Impedit, adipisci! Quisquam nostrum dignissimos tenetur consectetur eveniet. This is chat Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum eum, nesciunt veniam corrupti nulla nostrum? Nobis iure tempore ea pariatur!</SpeechSec>
        </div>
    </div>
</div>
<style>
    .pri{
        display: inline;
    }
    .sec{
        display: inline;
    }
    .inner{
        height: 100vh;
        width: 100vw;
        background-color: #F5EBE0;
        display: flex;
        justify-content: center;
    }
    
</style>