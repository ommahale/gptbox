<div class="outer">
    <div class="bubble">
        <slot>
        </slot>
    </div>
    <div class="inner">
        <div class="bar-1"></div>
        <div class="bar-2"></div>
    </div>
</div>
<style>
    *{
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif ;
    }
    .bubble{
        color: white;
        background-color: #344D67;
        padding: 10px;
        margin: 3px;
        display: inline-block;
        border-radius: 10px;
        max-width: 500px;
        box-shadow: 7px 7px 1px #E8C4C4;
    }
    .bar-1{
        width: 30px;
        height: 10px;
        display: block;
        margin: 2px;
        background-color: #344D67;
        border-radius: 30px;
        box-shadow: 7px 7px 1px #E8C4C4;
    }
    .inner{
        display: flex;
        flex-direction: column;
        align-items: flex-end;
    }
    .bar-2{
        width: 10px;
        display: block;
        height: 10px;
        margin: 2px;
        background-color: #344D67;
        border-radius: 30px;
        box-shadow: 7px 7px 1px #E8C4C4;
    }
    .outer{
        display: flex;
        justify-content: flex-end;
        flex-direction: column;
        align-items: flex-end;
    }
</style>