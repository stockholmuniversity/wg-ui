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

<h1>Användarvilkor</h1>

<p>
    För att använda vpn-tjänsten krävs att anslutna datorer skall ägas och förvaltas av universitetet i enlighet med rådande föreskrifter (t.ex. att den är är knuten till den centrala antivirus- och inventeringstjänsten). Det innebär att privata datorer inte godkänns för användning utom i undantagsfall under en övergångsperiod, då särskilda skäl föreligger.
</p>
<p>
    Ett absolut krav är att alla enheter skall ha ett uppdaterat operativsystem, samt ett uppdaterat virusskydd där det är tillämpligt. För att få ansluta en privat dator till vpn-tjänsten krävs dispens enligt ansökan från avdelningschef/prefekt till IT-avdelningen. Ett sådanat skäl kan t.ex. vara att du inte har en bärbar dator som arbetsstation på jobbet. Undantagen gäller fram till den 15 april, därefter måste ansökan förnyas.
</p>
<p>
    Samma krav för uppdateringar av operativsystem och virusskydd gäller för privata datorer som för universitetes arbetsstationer. Användning av vpn-tjänsten på privata mobila enheter godkänns dock under förutsättning att de har ett uppdaterat operativsystem.
</p>
<button on:click={_onOk}>
    Jag accepterar
</button>
<button on:click={_onCancel}>
    Avbryt
</button>
