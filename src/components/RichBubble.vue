<template>
    <div class="rich-bubble" tabindex="0" :class="{'me': me, 'loading': loading}">{{text}}</div>
</template>

<style lang="sass" scoped>
.rich-bubble
    padding: 12px
    border-radius: 40px
    color: var(--text-element)
    border: 1px solid var(--background-element)
    display: inline-block
    position: relative
    background-color: var(--background) !important
    min-width: 26px
    border-top-left-radius: 0
    word-wrap: break-word
    flex-grow: 0
    white-space: pre-wrap
    
    &::before
        content: var(--bubble-left)
        position: absolute
        left: 0
        top: 0
        margin-top: -9px
        margin-left: -1px
        
    &.me
        background-color: var(--background-element) !important
        border: 1px solid var(--background-element)
        color: var(--text-element)
        border-top-left-radius: 40px
        
        &::before
            content: ''
            
        &::after
            content: var(--bubble-right)
            position: absolute
            right: 0
            top: 0
            margin-top: -9px
            margin-right: -1px
    &.loading
        height: 16px
        background: url('~@/assets/svg/three-dots.svg') no-repeat
        background-size: 40px
        background-position: center
</style>

<script>
export default {
    name: 'RichBubble',
    props: {
        text: {
            type: String,
            required: false,
            default: ''
        },
        me: {
            type: Boolean
        },
        loading: {
            type: Boolean
        }
    }
}
</script>
