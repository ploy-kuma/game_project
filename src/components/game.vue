<template>
    <div>
        <p>
            HP Player {{ randomNo(1,3)}}
            {{ player[randomNo(1,3) - 1].name}}
        </p>
        +รูป
        <hr />
        name = {{ aPlayer.name}}
        hp = {{ aPlay.hp}}
        image = {{ aPlay.image}}
        <hr />
        <p>
            HP ตัวละคร 150
        </p>
        +รูป
        <button @click="start()">start</button>
        <button @click="attack()">Attack</button>
    </div>

</template>