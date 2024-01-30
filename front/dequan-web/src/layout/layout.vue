
import { Headers } from 'undici-types';

<template>
    <main>
        <Headers>头部</Headers>
        <div>
            <slot></slot>
        </div>
        <footer>尾部</footer>
    </main>
    
</template>