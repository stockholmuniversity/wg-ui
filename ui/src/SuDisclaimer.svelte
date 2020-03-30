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
    För att använda VPN-tjänsten krävs att anslutna datorer ska ägas och förvaltas av universitetet i enlighet med rådande föreskrifter, dvs att den är knuten till den centrala antivirus- och inventeringstjänsten.
Det innebär att datorer som inte ägs eller förvaltas av universitetet inte godkänns för användning av VPN-tjänsten.
<br/>
Ett absolut <b>krav</b> är att alla enheter som ansluts ska ha ett <b>uppdaterat operativsystem</b> samt ett <b>uppdaterat virusskydd</b> där det är tillämpligt.
</p>
<p>
    Endast i undantagsfall kan en dator som inte ägs eller förvaltas av universitetet anslutas och för det krävs ett dispensförfarande. Prefekt eller motsvarande ansöker om dispens hos IT-avdelningen genom att göra en beställning i serviceportalen. Där ska anledning till dispensen tydligt beskrivas.
</p>
<p>
Exempel på skäl till dispens kan t. ex. vara att du inte har en bärbar dator som arbetsdator, eller att du är konsult som måste arbeta med ett annat företags dator. Undantagen gäller då en månad i taget, därefter måste ansökan förnyas.
</p>
<p>
När det gäller uppdateringar av operativsystem och virusskydd gäller samma krav för icke universitetsägda datorer som för datorer som ägs och förvaltas av universitetet. Användning av VPN-tjänsten på mobila enheter godkänns dock under förutsättning att de har ett uppdaterat operativsystem.
</p>
<p
    <a href="https://arendehantering.su.se/AutoGen.aspx?page=194" target="_blank">Ansökan om dispens</a>
</p>



<h1>Terms of usage</h1>

<p>
    In order to use the VPN service, connected computers must be owned and managed by the university in accordance with prevailing regulations, i.e. it is linked to the central antivirus and inventory service.
This means that computers that are not owned or managed by the university are not approved for use of the VPN service.
<br/>
An absolute <b>requirement</b> is that all devices that are connected must have an <b>updated operating system</b> as well as an <b>updated virus protection</b> where applicable.
</p>
<p>
    Only in exceptional cases can a computer that is not owned or managed by the university be connected and for that a dispensation procedure is required. The head of department or equivalent applies for an exemption from the IT department by placing an order in the service portal. There, the reason for the exemption should be clearly described.
</p>
<p>
    Examples of reasons for dispensation may be e.g. be that you do not have a laptop as a work computer, or that you are a consultant who has to work with another company's computer. The exceptions then apply one month at a time, after which the application must be renewed.

</p>
<p>
When it comes to operating system updates and virus protection, the same requirements apply to non-university-owned computers as to computers owned and managed by the university. However, the use of the VPN service on mobile devices is approved provided they have an updated operating system.
</p>
<p
    <a href="https://arendehantering.su.se/AutoGen.aspx?page=194" target="_blank">Application for exemption</a>
</p>


<button on:click={_onOk}>
    Jag accepterar / I accept
</button>
<button on:click={_onCancel}>
    Avbryt / Cancel
</button>
