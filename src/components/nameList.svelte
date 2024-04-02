<script>
    const names= [
        {
            firstName: 'John',
            lastName: 'whike',
        },
        {
            firstName: 'Clark',
            lastName: 'kent',
        },
        {
            firstName:'princess',
            lastName: 'gayana',
        },

    ]
</script>


{#each names as name (name) }
    <!-- <h3>{name.firstName} {name.lastName}</h3> -->

    <slot name="hero" firstName={name.firstName} lastName={name.lastName}></slot>
{/each}
