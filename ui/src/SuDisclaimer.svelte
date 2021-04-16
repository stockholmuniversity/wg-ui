<script>
    import { getContext } from 'svelte';

    const { close } = getContext('simple-modal');

    function _onCancel() {
        window.location.href = "https://su.se";
    }

    function _onOk() {
        close();
    }


</script>

<style>
h1 {
    font-size: 2rem;
    text-align: center;
}

</style>

<h1>Användarvillkor</h1>


<p>
För att använda VPN-tjänsten <b>krävs</b> att alla enheter som ansluts ska ha ett <b>uppdaterat operativsystem</b> samt ett <b>uppdaterat virusskydd</b> där det är tillämpligt.
</p>



<h1>Terms of usage</h1>

<p>
In order to use the VPN service, an absolute <b>requirement</b> is that all devices that are connected must have an <b>updated operating system</b> as well as an <b>updated virus protection</b> where applicable.
</p>


<button on:click={_onOk}>
    Jag accepterar / I accept
</button>
<button on:click={_onCancel}>
    Avbryt / Cancel
</button>
