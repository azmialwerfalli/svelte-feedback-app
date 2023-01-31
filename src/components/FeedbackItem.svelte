<script>
    import {createEventDispatcher} from 'svelte'
    import Card from "./Card.svelte";
    export let item 
    const dispatch = createEventDispatcher()
    const handleDelete = (itemId) => {
        dispatch('delete-feedback', itemId)
    }
</script>

    <Card>
        <div class="num-display">
            {item.rating}
        </div>
        <button class="close" on:click={()=> handleDelete (item.id)}>X</button>
        <div class="text-display">
            {item.text}
        </div>
    </Card>
    <style>
        .num-display {
            position: absolute;
            inset: -10px auto auto -10px;
            width: 50px;
            height: 50px;
            background: #ff6aa8;
            color: #fff;
            border: 1px #eee solid;
            border-radius: 50%;
            padding: 10px;
            text-align: center;
            font-size: 1.1rem;
        }
        .close {
            position: absolute;
            inset: 10px 20px auto auto;
            cursor: pointer;
            background: none;
            border: none;
        }
    </style>
