<script setup lang="ts">
import {computed, ref, onMounted} from 'vue';

interface Expeditions {
    [index: string]: string;
}

interface RundownData {
    [index: string]: Expeditions;
}

const rundownData = ref<RundownData>({
    R1: {
        'ALT://R1A1': 'https://steamuserimages-a.akamaihd.net/ugc/1922499986457817123/91ED86D4D8522DE7CBBD1F9F4248E3D7BB677213/',
        'ALT://R1B1': 'https://steamuserimages-a.akamaihd.net/ugc/1922499986458158672/34E1989A010AB2FD196DD4EAC6D35D89ABFEF238/',
        'ALT://R1B2': 'https://steamuserimages-a.akamaihd.net/ugc/1922499986458539018/852AD279464FC4FD39E932A74951923DDA81C59A/',
        'ALT://R1C1': 'https://steamuserimages-a.akamaihd.net/ugc/1922499986462082834/A020ADB4C014FBDD8469C0AD74AA607238751C5E/',
        'ALT://R1C2': 'https://steamuserimages-a.akamaihd.net/ugc/1922499986462477140/490D176A198A8890AEDBFBC78C57A0293C60FCD9/',
        'ALT://R1D1': 'https://steamuserimages-a.akamaihd.net/ugc/1922499986463153320/1CB7656D1187CE34F193C63E8AFC0A573AE9DC70/',
    },
    R2: {
        'ALT://R2A1': 'https://steamuserimages-a.akamaihd.net/ugc/2018205919228656074/DDFA510078649FF8B8D662A972A9D97452CAEAA7/',
        'ALT://R2B1': 'https://steamuserimages-a.akamaihd.net/ugc/2018205919228953608/F589E56E2C5B09C4A54FE53FAC21A63D91E57500/',
        'ALT://R2B2': 'https://steamuserimages-a.akamaihd.net/ugc/2018205919229255742/4AF33F1EF20E97EFE69620941D0D3A3B2D36C0BA/',
        'ALT://R2B3': 'https://steamuserimages-a.akamaihd.net/ugc/2018205919229530141/B95495E79624A5E6E2DBAD40A0B894A735709F2F/',
        'ALT://R2B4': 'https://steamuserimages-a.akamaihd.net/ugc/2018205919229757476/498A2DC3EC55F580D48122213033EBE46B121A79/',
        'ALT://R2C1': 'https://steamuserimages-a.akamaihd.net/ugc/2018205919230092951/B08B0D5BE4F12043DED7DCE04E572C7A06350722/',
        'ALT://R2C2': 'https://steamuserimages-a.akamaihd.net/ugc/2018205919234928479/E927A75981025ABE2B0078A7ED1D4B2E7A34707B/',
        'ALT://R2D1': 'https://steamuserimages-a.akamaihd.net/ugc/2018206449575097173/B60015DE529C362C5C12B1AC5365F31EDF44561B/',
        'ALT://R2D2': 'https://steamuserimages-a.akamaihd.net/ugc/2018206449579261421/67C590B51328A03A9628F0CDD2C3FBB52C65079F/',
        'ALT://R2E1': 'https://steamuserimages-a.akamaihd.net/ugc/2018206449579693855/63BE49F90F0E934F9A42817D0634DD4C2F78B64D/',
    },
    R3: {
        'ALT://R3A1': 'https://steamuserimages-a.akamaihd.net/ugc/2049738728145297098/2455AE8616B009877C464107F796040BF6B230C0/',
        'ALT://R3A2': 'https://steamuserimages-a.akamaihd.net/ugc/2049738728145299606/040959F39F3277440002F3A90C77E295CF80DAC4/',
        'ALT://R3A3': 'https://steamuserimages-a.akamaihd.net/ugc/2049738728145300572/A20423D92CDEFFC397B0EB56208C608D5B5DA7F8/',
        'ALT://R3B1': 'https://steamuserimages-a.akamaihd.net/ugc/2049738728145301754/818F46282C85C729619EC2B3FD5656392F182B97/',
        'ALT://R3B2': 'https://steamuserimages-a.akamaihd.net/ugc/2049738728145303229/4CE3722FE866D9F718482C2472A328ED977CEE5F/',
        'ALT://R3C1': 'https://steamuserimages-a.akamaihd.net/ugc/2049738728145305864/E5A02FF9B7B60456A4E851084F15DCFCCAF1761C/',
        'ALT://R3D1': 'https://steamuserimages-a.akamaihd.net/ugc/2049738728145306915/F8AB646ABBEB23D68C00481AEC1670EA6C9E1A88/',
    },
    R4: {
        'ALT://R4A1': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162856869/9A7A7ABF0201CCFAFB1C5DF73DA208C6252B7916/',
        'ALT://R4A2': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162857636/D707CDA1E3A97E792A69F0B3E693DFA1229317D6/',
        'ALT://R4A3': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162859245/F056D6B373AADD45E90EC1E8EEE13DA74307F986/',
        'ALT://R4B1': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162860579/7BE949DDE797CD4B5518898324F45F45E13A234A/',
        'ALT://R4B2': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162861493/DABCCB85F4B54A5CFE32FAC180BBE763F2A3C4C1/',
        'ALT://R4B3': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162864020/14206F21B082570245F51C7E005BA13FB7997A7D/',
        'ALT://R4C1': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162865087/D16BC1F5E8522BD27E9DFED60888393E46B63E80/',
        'ALT://R4C2': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162866023/A44A97552368BEB17099544C1CE1C67B618660E7/',
        'ALT://R4C3': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162867116/B33549AB8511B0B0952B2BA3AE19C1ADC830E712/',
        'ALT://R4D1': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162868143/8173CD9DEE8963CD483D1D63458863BAE9AFE08C/',
        'ALT://R4D2': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162869100/AC3D6A2D4FF3FEF86FD8F366C1FC76155482D9E7/',
        'ALT://R4E1': 'https://steamuserimages-a.akamaihd.net/ugc/2070009996162870039/A34B2E4EB93F9E0A0009473D2A83540DA06A2183/',
    },
    R5: {
        'ALT://R5A1': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555600131909/86698319C990BBC440F4CEFA46DC6A7C0AD8A9F6/',
        'ALT://R5A2': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555600133267/304DDD1B067ED31F810B30A1835F4BFA7ACB4D65/',
        'ALT://R5A3': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555600134506/C2D7CAE6C5ED85DC9658470907A6148DBC35BF5E/',
        'ALT://R5B1': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555600135309/B26F53B425CD8B33B20619187CB21DBA0B210BF6/',
        'ALT://R5B2': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555603483697/56E1AF72077E679B736939F4B10D8FA664B10451/',
        'ALT://R5B3': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555603575457/CC51ADD9CEFEDA406C04450DD729EC4E6E37E101/',
        'ALT://R5B4': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555603699030/942FCCA716681920C066001D3A1E999A9E595C8B/',
        'ALT://R5C1': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555603802602/3CA75EE8209DE6365F0EF21C1BB2DDBE30692EC8/',
        'ALT://R5C2': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555603951685/8EEAC8899F9F576988AD2CE75FE812FB5A6D69CB/',
        'ALT://R5C3': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555604074452/46E1AC68C4559DB3D9F312743F97ADFEB65C280A/',
        'ALT://R5D1': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555604173537/476293F6A8278CBA2494AA836E92BE6A0E532484/',
        'ALT://R5D2': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555604299138/22341518F7494AA824630CE6FB4E477E4064FF17/',
        'ALT://R5E1': 'https://steamuserimages-a.akamaihd.net/ugc/2054252555604438647/E195278BEC8D93E9A694B668292B949561ACD703/',
    },
    R6: {
        'ALT://R6A1': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909109190708/667A7F65C8898FADBD855F0C90A7BEB0A3ECEF8B/',
        'ALT://R6AX': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909109198588/C7F0776FCF77629092041226DB7933D280EEA328/',
        'ALT://R6B1': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909109193590/06E2EAC87A001804F64EAC69EBD029D37D8A9BAF/',
        'ALT://R6B2': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909109196573/B9388298EF313936345E75A158ACA117124BBE0B/',
        'ALT://R6BX': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909109205189/A1712B0E8B7B6FDAE898265D3E67EB47868C840F/',
        'ALT://R6C1': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909112724559/1F1BEEB6D1C65B76888357BE7519D8C6F8368096/',
        'ALT://R6C2': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909112857500/0FE82503DE8DBA53EB9F4E3756AE9F9FD4AF1E0D/',
        'ALT://R6C3': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909112999985/57DF816163060DAF061AA1124D783BCE52B42BE0/',
        'ALT://R6CX': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909113089373/3801B4EA942638695EC3F295153388995FF3C842/',
        'ALT://R6D1': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909113199594/96C536062078CA9DAEED7FB0804E618C018064CE/',
        'ALT://R6D2': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909113283669/7F30A62CEEEE50B5009C5E82DAAA6AAB886C1CB0/',
        'ALT://R6D3': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909113433448/BF2DEB3DAEB8E9862DC5D40C3981841E479A549F/',
        'ALT://R6D4': 'https://steamuserimages-a.akamaihd.net/ugc/2119562909113593099/064F677CF347A0E13739975F6F30B05BF4009701/',
    },
    R7: {
        A1: 'https://steamuserimages-a.akamaihd.net/ugc/1862817291122574903/1F063993285AB685970E4480DA390B330AF2D51D/',
        B1: 'https://steamuserimages-a.akamaihd.net/ugc/1862817291123230672/317DE30ABE11BC7BDDC6ED12070EF7088B59F339/',
        B2: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412066983268/667C500A6D1ED4D205AD5E774D7F6179A2B40048/',
        B3: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412071096239/CC2E55A8CB2EE2594D605DCB33052B38E9A43A11/',
        C1: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412075777894/9CF29F4DC3744EC77B689A37B19783DFFF178FE2/',
        C2: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412076102106/F7D56DCBDD5301F643631C9CDBA1149CC7DBE971/',
        C3: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412080664833/E3D7BE440F4C716936E26DE8502E7CE63F5445E1/',
        D1: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412082706103/17F28C26F168E55EB6A7FDB9A79A3BE3E644C02C/',
        D2: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412085449684/092F2F3A889F630E7E7339FA696C3248C602B6D5/',
        E1: 'https://steamuserimages-a.akamaihd.net/ugc/1862817412086580952/ED302BA72B0FA3D3500D1852327368242738AD96/',
    },
    R8: {
        A1: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690768594/2D382004C2E6E28EFCB15095712C6F23EE9AE5EA/',
        A2: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690769779/59843B562F0D26287045A8C606CFAFEA2C132A85/',
        B1: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690771657/3FFD67CB49D17BB1241C93DD13CCB8E879395E5E/',
        B2: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690774225/AD4B5A393E7569A32177B5BAD10516F0632C8F84/',
        B3: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690775615/B3B418F1339713C356132CA3EC5078CF22990D55/',
        B4: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690777243/3AB12DAD23A0CB87E98190CDAC9DB01C58DD4DF7/',
        C1: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690779414/7CB78C45EF27E921251650081C7DBDA4390CCE8F/',
        C2: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241690781654/C730BF52BCED1BFAB9BF391AA79AF0523DB72359/',
        D1: 'https://steamuserimages-a.akamaihd.net/ugc/2309848621041203291/A4A3E1A9DFAF1063B4D87D47A67429284B668AB3/',
        D2: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241691951511/BBE3090E4ED80396BB9B598B63BD6A4FCFD29168/',
        E1: 'https://steamuserimages-a.akamaihd.net/ugc/2309848241697253959/EFFB5B6FE6AD7A9F51AAE5599884B03C4A91264F/',
        E2: 'https://steamuserimages-a.akamaihd.net/ugc/2309848621041183199/AB4E8CCB6BD70F9B4BA220B52210FF0DD56C8794/',
    },
});
const rundowns = computed(() => {
    return Object.keys(rundownData.value);
});

function expeditionList(rundown: string) {
    return Object.keys(rundownData.value[rundown]);
}

const selectedRundown = ref<string>();

function setSelectedRundown(rundown: string) {
    if (selectedRundown.value) {
        const previous = document.querySelector(`#rundowns-${selectedRundown.value}`);
        previous?.classList.remove('yellow');
        if (selectedExpedition.value) {
            const expedition = document.querySelector(`#expeditions-${cleanExpeditionName(selectedExpedition.value)}`);
            expedition?.classList.remove('yellow');
        }
    }
    selectedRundown.value = rundown;
    const current = document.querySelector(`#rundowns-${rundown}`);
    current?.classList.add('yellow');
}

const selectedExpedition = ref<string>();
const selectedImage = ref<string>();

function setSelectedExpedition(expedition: string) {
    if (selectedExpedition.value) {
        const previous = document.querySelector(`#expeditions-${cleanExpeditionName(selectedExpedition.value)}`);
        previous?.classList.remove('yellow');
    }
    selectedExpedition.value = expedition;
    const current = document.querySelector(`#expeditions-${cleanExpeditionName(expedition)}`);
    current?.classList.add('yellow');
    if (selectedRundown.value) {
        selectedImage.value = rundownData.value[selectedRundown.value][selectedExpedition.value]
    }
    else {
        selectedImage.value = undefined;
    }
}

function cleanExpeditionName(expedition: string) {
    return expedition.replace('://', '---');
}

onMounted(() => {
    const imgContainer = document.querySelector<HTMLDivElement>('#imgContainer');
    const zoomedArea = document.querySelector<HTMLDivElement>('#zoomedImage');
    const image = document.querySelector<HTMLImageElement>('#image');
    const width = 888;
    const height = 500;
    imgContainer?.addEventListener('mousemove', ((e: MouseEvent) => {
        if (imgContainer && zoomedArea && image && enableHover.value) {
            const offset = imgContainer.getBoundingClientRect();
            const mouseX = e.pageX - offset.left;
            const mouseY = e.pageY - offset.top;
            const imageWidth = image.clientWidth;
            const imageHeight = image.clientHeight;
            const zoomX = (mouseX / imageWidth) * 100;
            const zoomY = (mouseY / imageHeight) * 100;
            const widthScale = image.naturalWidth / width * 100;
            const heightScale = image.naturalHeight / height * 100;
            const left = Math.max(Math.min(e.pageX - (width / 2), window.innerWidth - width), 0);
            const top = Math.max(Math.min(e.pageY - (height / 2), window.innerHeight - height), 0);
            const style = `width: ${width}px; height: ${height}px; left: ${left}px; top: ${top}px; background: url(${image.getAttribute('src')}); background-size: ${widthScale}% ${heightScale}%; background-position: ${zoomX}% ${zoomY}%; display: block;`;
            zoomedArea.setAttribute('style', style);
        }
    }) as EventListener);
    imgContainer?.addEventListener('mouseleave', () => {
        zoomedArea?.setAttribute('style', 'display: none;');
    })
});

const enableHover = ref<boolean>(false);

</script>

<template>
    <div class="d-flex">
        <div>
            <h3 class="fw-bold">RUNDOWNS</h3>
            <div style="margin-bottom: 1em;">
                <input type="checkbox" v-model="enableHover"> Enable Zoom on Hover
            </div>
            <div class="d-flex">
                <div class="me-3" style="width: 100px;">
                    <h5 class="menu-item clickable p-2"
                        v-for="rundown of rundowns"
                        :key="rundown"
                        :id="`rundowns-${rundown}`"
                        @click="setSelectedRundown(rundown)"
                    >{{ rundown }}</h5>
                </div>
                <div v-if="selectedRundown">
                    <h5 class="menu-item clickable p-2"
                        v-for="expedition of expeditionList(selectedRundown)"
                        :key="expedition"
                        :id="`expeditions-${cleanExpeditionName(expedition)}`"
                        @click="setSelectedExpedition(expedition)"
                    >{{ expedition }}</h5>
                </div>
            </div>
        </div>
        <div id="imgContainer" class="ms-auto">
            <img id="image" :src="selectedImage" :alt="`${selectedExpedition} Map`" :style="`max-width: 100%;`"/>
        </div>
    </div>
    <div id="zoomedImage"></div>
</template>

<style scoped>
#zoomedImage {
    overflow: hidden;
    position: absolute;
    border: 2px solid black;
    pointer-events: none;
    display: none;
}
.yellow {
    color: yellow;
}
</style>