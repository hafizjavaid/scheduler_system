<template>
  <div class="main_cards">
    <div
      class="main_card"
      v-for="(card, i) in cards"
      :key="i"
      @click="gotoAddress"
    >
      <span v-html="card.svg">
        {{ card.svg }}
      </span>
      <h4>{{ card.title }}</h4>
      <span>
        <span v-html="card.svg1">
          {{ card.svg1 }}
        </span>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          svg: `<svg width="42" height="40" viewBox="0 0 42 40" fill="none" xmlns="http://www.w3.org/2000/svg">
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M32.8922 8.69816C31.5348 8.57994 30.5309 7.38972 30.6497 6.03994C30.7686 4.68972 31.9651 3.69149 33.3221 3.80972C34.679 3.92794 35.6835 5.11772 35.5646 6.46749C35.4458 7.81772 34.2492 8.81638 32.8922 8.69816ZM39.9076 13.5542L38.5261 5.10083C37.9068 2.36616 35.3412 0.515048 32.5361 0.778604L24.0285 2.09549C22.4262 2.24616 20.9665 3.0746 20.0219 4.3706L5.11237 24.8151C4.41803 25.7671 4.63116 27.0982 5.58777 27.7884L21.0782 38.9666C22.0352 39.6568 23.3734 39.4448 24.0678 38.4933L38.9773 18.0488C39.9223 16.7533 40.2615 15.1155 39.9076 13.5542Z" fill="#F27F0B"/>
<path opacity="0.3" fill-rule="evenodd" clip-rule="evenodd" d="M30.7463 5.12812C30.8879 6.47123 29.9617 7.66856 28.6775 7.80278C27.393 7.93745 26.2371 6.95745 26.095 5.61434C25.9529 4.27123 26.8791 3.07345 28.1637 2.93923C29.4478 2.805 30.6042 3.785 30.7463 5.12812ZM32.68 23.5486L35.6312 16.8637C35.616 16.6908 35.6008 16.5183 35.5731 16.3463L34.6147 7.55167C34.0759 4.33256 31.3499 2.02189 28.2683 2.13745C28.2557 2.13789 19.8155 2.99034 19.8155 2.99034C19.4442 3.00545 19.0805 3.06323 18.724 3.14634C17.4792 3.66189 16.4645 4.65523 15.8984 5.937L8.38215 26.0494C7.91479 27.109 8.3616 28.3726 9.38032 28.8726L21.1153 38.9508L32.68 23.5486Z" fill="#1C1F34"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M32.8922 8.69816C31.5348 8.57994 30.5309 7.38972 30.6497 6.03994C30.7686 4.68972 31.9651 3.69149 33.3221 3.80972C34.679 3.92794 35.6835 5.11772 35.5646 6.46749C35.4458 7.81772 34.2492 8.81638 32.8922 8.69816ZM39.9076 13.5542L38.526 5.10083C37.9068 2.36616 35.3412 0.515048 32.5361 0.778604L24.0285 2.09549C22.4262 2.24616 20.9665 3.0746 20.0219 4.3706L5.11237 24.8151C4.41803 25.7671 4.63116 27.0982 5.58777 27.7884L21.0782 38.9666C22.0352 39.6568 23.3734 39.4448 24.0678 38.4933L38.9773 18.0488C39.9223 16.7533 40.2615 15.1155 39.9076 13.5542Z" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M34.982 8.00485C35.9453 7.04663 35.9453 5.4933 34.982 4.53507C34.0186 3.57685 32.457 3.57685 31.4937 4.53507C30.5304 5.4933 30.5304 7.04663 31.4937 8.00485C32.457 8.96307 34.0186 8.96307 34.982 8.00485Z" fill="white"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M34.982 8.00485C35.9453 7.04663 35.9453 5.4933 34.982 4.53507C34.0186 3.57685 32.457 3.57685 31.4937 4.53507C30.5304 5.4933 30.5304 7.04663 31.4937 8.00485C32.457 8.96307 34.0186 8.96307 34.982 8.00485Z" stroke="#3A427C" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M34.982 8.0049C34.0187 8.96313 32.4571 8.96313 31.4937 8.0049C30.5304 7.04668 30.5304 5.49335 31.4937 4.53513C32.4571 3.5769 34.0187 3.5769 34.982 4.53513C35.9453 5.49335 35.9453 7.04668 34.982 8.0049ZM38.8589 15.0093L38.829 6.11424C38.6427 3.2089 36.3153 0.893348 33.3945 0.708014L24.452 0.678237C22.7841 0.572459 21.1506 1.18579 19.9688 2.36135L1.32122 20.9102C0.453068 21.7738 0.453068 23.1738 1.32122 24.0373L15.376 38.0173C16.2442 38.8809 17.6516 38.8809 18.5198 38.0173L37.1673 19.4685C38.3491 18.2929 38.9653 16.6685 38.8589 15.0093Z" fill="white"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M34.982 8.0049C34.0187 8.96313 32.4571 8.96313 31.4937 8.0049C30.5304 7.04668 30.5304 5.49335 31.4937 4.53513C32.4571 3.5769 34.0187 3.5769 34.982 4.53513C35.9453 5.49335 35.9453 7.04668 34.982 8.0049ZM38.8589 15.0093L38.829 6.11424C38.6427 3.2089 36.3153 0.893348 33.3945 0.708014L24.452 0.678237C22.7841 0.572459 21.1506 1.18579 19.9688 2.36135L1.32122 20.9102C0.453068 21.7738 0.453068 23.1738 1.32122 24.0373L15.376 38.0173C16.2442 38.8809 17.6516 38.8809 18.5198 38.0173L37.1673 19.4685C38.3491 18.2929 38.9653 16.6685 38.8589 15.0093Z" stroke="#1C1F34" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M23.0468 3.81641L35.7045 16.4071" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M18.8115 32.0133L17.3911 30.6004C15.2943 32.1849 13.0776 31.7227 11.8302 30.7195L13.0776 28.6867C13.9936 29.4387 15.3206 29.6502 16.5417 28.4351C17.4045 27.5773 17.4975 26.6667 16.913 26.0853C16.4627 25.6369 15.7853 25.6235 14.9761 26.1387L13.4896 27.0893C11.7372 28.1978 9.94551 28.1849 8.67166 26.9173C7.26466 25.5182 7.31828 23.4062 8.5126 21.7689L7.09219 20.356L8.44602 19.0098L9.90619 20.4622C11.7109 19.2209 13.4364 19.6169 14.511 20.3164L13.3435 22.4022C12.7988 22.0195 11.684 21.5969 10.5956 22.6795C9.74624 23.524 9.77304 24.4751 10.3173 25.0164C10.7288 25.4258 11.3659 25.4787 12.1224 24.9898L13.6089 24.0658C15.6526 22.772 17.405 23.0098 18.5989 24.1978C19.8204 25.4124 20.0724 27.4062 18.732 29.2413L20.1654 30.6671L18.8115 32.0133Z" fill="#AB651E"/>
<path d="M19.8329 21.8772L28.3706 13.3848" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M24.4047 26.4253L32.9423 17.9329" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M22.1188 24.1512L30.6564 15.6592" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M17.5471 19.6035L26.0847 11.1111" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M15.2612 17.3298L23.7988 8.8374" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M12.9753 15.0559L21.513 6.56348" stroke="#1C1F34" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="42" height="40" fill="white"/>
</clipPath>
</defs>
</svg>
`,
          title: "Store Delivery",
          svg1: `<svg width="37" height="37" viewBox="0 0 37 37" fill="none" xmlns="http://www.w3.org/2000/svg">
<circle cx="18.5" cy="18.5" r="18.5" fill="white"/>
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.031 20H26.111L20.439 25.743C20.136 26.017 20.437 26.478 20.721 26.771C20.869 26.923 21.068 27 21.268 27C21.452 27 21.637 26.935 21.781 26.803L29.766 19.53C29.826 19.47 29.836 19.436 29.857 19.407C29.899 19.344 29.926 19.318 29.94 19.287C29.964 19.224 29.967 19.179 29.975 19.135C29.983 19.093 29.999 19.053 30 19.01C29.999 18.946 29.983 18.906 29.975 18.864C29.966 18.819 29.964 18.775 29.947 18.733C29.926 18.681 29.899 18.656 29.881 18.626C29.836 18.562 29.826 18.529 29.8 18.502C29.77 18.476 21.782 11.197 21.782 11.197C21.481 10.923 21.007 10.936 20.722 11.229C20.438 11.521 20.137 11.982 20.439 12.257L26.111 18H7.031C6.617 18 6 18.598 6 19C6 19.401 6.617 20 7.031 20Z" fill="#283060"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="24" height="16" fill="white" transform="translate(6 11)"/>
</clipPath>
</defs>
</svg>
`,
        },
        {
          svg: `<svg width="56" height="40" viewBox="0 0 56 40" fill="none" xmlns="http://www.w3.org/2000/svg">
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M4.56022 24.2336L9.41561 8.74009L5.52503 7.55591C5.52503 7.55591 3.53608 9.46986 1.66388 14.954C-0.208323 20.4387 0.725169 22.7075 0.725169 22.7075L4.56022 24.2336Z" fill="#AB651E"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M9.46445 9.6599L5.06371 23.6436L8.77489 24.9143L11.2417 27.8101C11.2417 27.8101 10.6305 28.8185 10.6836 29.2971C10.7368 29.7757 11.5635 30.9385 11.5635 30.9385L13.4348 31.2525L14.709 33.2576L17.2802 33.572L18.1796 35.8483L20.3693 36.1692L21.6535 37.8911L23.4583 38.212L24.9266 36.5669L28.0028 38.8911C28.0028 38.8911 30.3154 40.065 31.9556 37.4418C31.9556 37.4418 36.3929 38.5873 36.4057 35.1278C36.4057 35.1278 38.5194 36.5455 40.1572 35.1278C41.795 33.7101 41.3365 32.5813 41.3365 32.5813C41.3365 32.5813 43.4166 33.3548 44.3529 31.7869C45.2897 30.219 43.811 28.4352 43.811 28.4352L47.291 24.9143L50.9832 23.4171L46.7116 10.0106L41.6607 11.1841C41.6607 11.1841 37.9571 11.6636 35.1718 10.6669C32.3865 9.66967 28.0237 10.6669 28.0237 10.6669C28.0237 10.6669 24.9152 9.23711 20.7541 9.35479C16.5935 9.47199 14.1794 10.9971 11.8217 10.3283L9.46445 9.6599Z" fill="#E7EBF6"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M10.9176 28.4359C10.9176 28.4359 10.0634 30.0986 11.5635 30.9391C13.0637 31.7796 13.8757 31.2531 13.8757 31.2531C13.8757 31.2531 13.6232 32.5065 14.709 33.2582C15.7949 34.0103 17.5366 33.2582 17.5366 33.2582C17.5366 33.2582 17.1882 35.3451 18.1796 35.8489C19.171 36.3526 20.5748 35.8489 20.5748 35.8489C20.5748 35.8489 20.4941 37.0884 21.6535 37.8917C22.8129 38.6945 24.3301 37.5791 24.3301 37.5791L26.9317 33.5726C26.9317 33.5726 27.1752 32.1884 25.9992 31.3703C24.8232 30.5526 23.4578 31.2531 23.4578 31.2531C23.4578 31.2531 23.4578 30.0693 22.5092 29.4C21.561 28.7307 19.5881 29.5117 19.5881 29.5117C19.5881 29.5117 19.5127 28.1665 18.3747 27.5377C17.2361 26.9089 16.4379 27.5377 16.4379 27.5377C16.4379 27.5377 16.4778 25.9052 15.1879 25.2359C13.898 24.567 12.5326 26.0912 12.5326 26.0912L10.9176 28.4359Z" fill="white"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M46.7116 10.0107C46.7116 10.0107 41.5354 12.1084 38.06 11.6219C34.5852 11.1354 32.1354 9.04283 28.0237 10.667C23.9115 12.2907 23.1669 13.0814 22.4223 14.48C21.6777 15.8791 20.188 18.5549 20.188 18.5549C20.188 18.5549 19.1225 19.9707 20.3693 21.0875C21.6155 22.2042 24.5474 21.4424 25.5948 20.1814C26.6417 18.92 27.2625 17.3386 27.2625 17.3386L30.8617 17.0954C30.8617 17.0954 32.6613 19.7107 34.3987 21.4135C36.1366 23.1163 43.811 28.4359 43.811 28.4359L47.291 24.9149L50.8423 23.8889L46.7116 10.0107Z" fill="white"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M51.3458 24.5739L55.1752 23.2097C55.1752 23.2097 55.6811 21.0851 54.1482 14.9823C52.6149 8.87903 50.381 7.89624 50.381 7.89624L46.7116 9.01298L51.3458 24.5739Z" fill="#AB651E"/>
<path opacity="0.2" fill-rule="evenodd" clip-rule="evenodd" d="M31.4967 18.0824C31.4141 17.8935 31.361 17.6982 31.323 17.5014C31.2414 17.4326 31.1939 17.3875 31.1915 17.3847C31.0349 17.2298 30.819 17.1591 30.6073 17.1949L26.9488 17.801C26.6546 17.8493 26.4225 18.0926 26.3717 18.4019C26.348 18.5452 25.7581 21.9098 22.5979 22.2354C21.9947 22.2968 20.9359 22.308 20.6222 21.6782C20.5145 21.4619 20.4922 21.168 20.5344 20.8391C20.0191 20.587 19.6048 20.1075 19.4875 19.4033C19.0803 20.3959 18.9532 21.4796 19.3921 22.361C19.7149 23.008 20.4414 23.7293 22.0768 23.7293C22.2809 23.7293 22.4997 23.7177 22.7332 23.6945C25.7757 23.3814 27.1913 20.8405 27.6298 19.1721L30.5096 18.6954C30.8797 19.0052 31.6177 19.5554 32.6627 20.0242C32.2066 19.4684 31.817 18.8163 31.4967 18.0824Z" fill="#3A427C"/>
<path d="M46.7116 10.0205L41.9673 11.3121C41.9673 11.3121 38.6775 12.1424 35.4907 10.9619C32.1369 9.72004 29.4427 9.72934 25.8302 11.5447C21.4039 13.7693 22.3915 15.5256 20.9279 17.2293C19.4643 18.9326 18.9152 21.8912 22.6658 21.5326C26.4163 21.174 27.0565 17.4084 27.0565 17.4084L30.7155 16.8456C30.7155 16.8456 32.6461 18.6252 35.8253 18.8698" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M30.7155 16.8457C35.2064 23.4466 43.3392 28.4359 43.3392 28.4359C43.3392 28.4359 45.6509 29.8155 44.3529 31.7876C43.0545 33.7597 40.6977 32.4876 40.6977 32.4876C40.6977 32.4876 41.8215 34.0141 39.9394 35.2866C38.0567 36.5587 35.8946 34.9685 35.8946 34.9685C35.8946 34.9685 36.8238 36.368 35.3308 37.322C33.8378 38.2764 31.481 37.322 31.481 37.322C31.481 37.322 32.1502 38.5308 30.268 39.1671C28.3853 39.8029 26.8278 37.9583 26.8278 37.9583L25.5944 36.7494" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M22.5585 29.3153C21.6383 28.7227 20.4016 28.9734 19.797 29.8758L17.6077 33.1423C17.0031 34.0446 17.2589 35.2562 18.1796 35.8488C19.0998 36.4413 20.3361 36.1902 20.9407 35.2883L23.1304 32.0213C23.735 31.1195 23.4787 29.9078 22.5585 29.3153Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M26.0324 31.3583C25.1122 30.7657 23.8759 31.0164 23.2713 31.9187L21.0816 35.1852C20.477 36.0876 20.7328 37.2992 21.6535 37.8917C22.5737 38.4843 23.81 38.2331 24.4146 37.3313L26.6043 34.0643C27.2089 33.1624 26.9526 31.9508 26.0324 31.3583Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M18.5446 27.5587C17.6443 26.9792 16.4346 27.2243 15.8433 28.1071L14.1495 30.6108C13.5582 31.4931 13.8083 32.6787 14.709 33.2583C15.6093 33.8378 16.8185 33.5922 17.4098 32.7099L19.1041 30.2062C19.6954 29.3238 19.4448 28.1383 18.5446 27.5587Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M15.3055 25.2289C14.4053 24.6494 13.1956 24.8945 12.6043 25.7773L11.004 28.2917C10.4127 29.174 10.6628 30.3591 11.5635 30.9387C12.4638 31.5187 13.673 31.2731 14.2643 30.3908L15.8651 27.8763C16.4564 26.994 16.2058 25.8084 15.3055 25.2289Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M11.2418 27.8103C11.2418 27.8103 10.2143 25.4792 8.53952 24.8066C5.84583 23.7248 4.76332 23.5857 4.76332 23.5857" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M28.551 10.4692C28.551 10.4692 22.8893 8.70644 18.7728 9.61434C14.6568 10.5222 15.335 11.4185 9.46448 9.65946" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M43.3392 28.4357C43.3392 28.4357 45.6913 27.6027 47.6019 24.425" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M40.6978 32.4871C40.6978 32.4871 36.242 29.6457 30.8574 24.1982" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M36.3691 34.9678C36.3691 34.9678 31.0136 31.1609 27.7129 27.5376" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M31.9556 37.3218C31.9556 37.3218 29.186 35.2725 26.9298 32.9343" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M47.0376 25.2554L50.3796 23.8889" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M51.3458 24.5739L46.4904 9.08043L50.381 7.89624C50.381 7.89624 55.5439 13.24 55.1752 23.2097L51.3458 24.5739Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M4.56021 24.2336L9.4156 8.74009L5.52503 7.55591C5.52503 7.55591 0.362112 12.9001 0.730858 22.8694L4.56021 24.2336Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M25.4781 3.36426L26.5824 6.33635" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M29.4427 6.75775L31.9556 0.697754" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="56" height="40" fill="white"/>
</clipPath>
</defs>
</svg>

`,
          title: "Store Delivery",
          svg1: `<svg width="37" height="37" viewBox="0 0 37 37" fill="none" xmlns="http://www.w3.org/2000/svg">
<circle cx="18.5" cy="18.5" r="18.5" fill="white"/>
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.031 20H26.111L20.439 25.743C20.136 26.017 20.437 26.478 20.721 26.771C20.869 26.923 21.068 27 21.268 27C21.452 27 21.637 26.935 21.781 26.803L29.766 19.53C29.826 19.47 29.836 19.436 29.857 19.407C29.899 19.344 29.926 19.318 29.94 19.287C29.964 19.224 29.967 19.179 29.975 19.135C29.983 19.093 29.999 19.053 30 19.01C29.999 18.946 29.983 18.906 29.975 18.864C29.966 18.819 29.964 18.775 29.947 18.733C29.926 18.681 29.899 18.656 29.881 18.626C29.836 18.562 29.826 18.529 29.8 18.502C29.77 18.476 21.782 11.197 21.782 11.197C21.481 10.923 21.007 10.936 20.722 11.229C20.438 11.521 20.137 11.982 20.439 12.257L26.111 18H7.031C6.617 18 6 18.598 6 19C6 19.401 6.617 20 7.031 20Z" fill="#283060"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="24" height="16" fill="white" transform="translate(6 11)"/>
</clipPath>
</defs>
</svg>
`,
        },
        {
          svg: `<svg width="47" height="40" viewBox="0 0 47 40" fill="none" xmlns="http://www.w3.org/2000/svg">
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M5.74133 19.0067L23.406 4.29565L41.2952 19.0067V39.0655H5.74133V19.0067Z" fill="#AB651E"/>
<path opacity="0.2" fill-rule="evenodd" clip-rule="evenodd" d="M33.5617 13.3918L23.8587 5.5509C23.8582 5.55045 23.8578 5.55045 23.8578 5.55045C23.7848 5.49157 23.7026 5.44888 23.6155 5.42371C23.6045 5.42056 23.5931 5.42011 23.5822 5.41742C23.5498 5.40933 23.5169 5.40169 23.4836 5.39854C23.474 5.39764 23.4644 5.39899 23.4548 5.39854C23.4197 5.39674 23.3846 5.39539 23.3494 5.39899C23.3485 5.39899 23.3472 5.39944 23.3462 5.39944C23.2504 5.40933 23.1564 5.44034 23.0697 5.49023C23.0382 5.5082 23.0072 5.52663 22.9785 5.54955C22.978 5.55 22.9775 5.55045 22.9766 5.5509L6.31171 19.0215C6.3254 19.6039 6.3327 20.1873 6.33543 20.7729L23.4174 6.96528L32.4793 14.288C32.723 13.8745 33.1049 13.5401 33.5617 13.3918Z" fill="#3A427C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M15.4593 23.7753L29.5169 12.3105L43.7529 23.7753V39.4081H15.4593V23.7753Z" fill="#E8EBF7"/>
<path opacity="0.2" fill-rule="evenodd" clip-rule="evenodd" d="M30.0056 14.0364C30.0047 14.0364 30.0047 14.036 30.0042 14.036C29.939 13.9825 29.8646 13.9443 29.7857 13.9214C29.7752 13.9182 29.7656 13.9178 29.7555 13.9155C29.7259 13.9083 29.6962 13.9016 29.6661 13.8984C29.657 13.898 29.6488 13.8989 29.6401 13.8984C29.6082 13.8971 29.5762 13.8958 29.5452 13.8989C29.5438 13.8989 29.5429 13.8993 29.5415 13.8993C29.4548 13.9083 29.37 13.9362 29.291 13.9816C29.2632 13.9978 29.2344 14.0144 29.2089 14.0355C29.2084 14.036 29.2075 14.036 29.2071 14.0364L15.4429 25.1591C15.4557 25.6863 15.4625 26.2144 15.4653 26.7443L29.6063 15.3169L43.9313 26.8931C43.9354 26.3641 43.9427 25.8351 43.9518 25.3061L30.0056 14.0364Z" fill="#3A427C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M32.5783 39.2903H39.1596V31.1245H32.5783V39.2903Z" fill="#AB651E"/>
<path d="M2.40839 39.3259H46.2001" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M5.70389 19.5505V39.3258H42.6651" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M15.7427 24.0449V39.3258H44.0362V24.0449" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M45.2998 21.8068V25.5084L29.6063 12.827L13.9129 25.5084V21.8068L29.6063 9.125" fill="#3A427C"/>
<path d="M45.2998 21.8068V25.5084L29.6063 12.827L13.9129 25.5084V21.8068L29.6063 9.125" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M16.3218 6.04897V4.63818H11.7221V9.76582" fill="#AEB8E0"/>
<path d="M16.199 6.07899V4.71899H11.6359V9.66281" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M32.6262 39.3257H39.0146V31.2358H32.6262V39.3257Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M32.6262 29.3977L35.8204 27.1909L39.0146 29.3977V30.7864H32.6262V29.3977Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path opacity="0.2" fill-rule="evenodd" clip-rule="evenodd" d="M28.242 34.3222V34.7172H19.6707V34.493C19.2116 34.675 18.6983 34.7109 18.2524 34.5388V35.3357C18.2524 35.6781 18.57 35.955 18.9615 35.955H28.9511C29.3426 35.955 29.6602 35.6781 29.6602 35.3357V34.1572C29.2349 34.3514 28.7216 34.4062 28.242 34.3222Z" fill="#3A427C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M18.7087 33.7078H28.2913V25.1685H18.7087V33.7078Z" fill="white"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M18.9369 34.3821H28.9757V25.3933H18.9369V34.3821Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M23.9563 25.6113V34.156" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M19.019 29.8877H28.8288" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M4.72738 19.8579L2.46454 22.0867" stroke="#3A427C" stroke-width="1.462" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M45.2998 21.8067L23.3723 4.23003L4.03244 19.8579V16.3024L23.3723 0.674072L36.1832 11.0269V14.4992" fill="#3A427C"/>
<path d="M45.2998 21.8067L23.3723 4.23003L4.03244 19.8579V16.3024L23.3723 0.674072L36.1832 11.0269V14.4992" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M5.7112 3.21045C2.935 3.21045 0.684479 28.1772 0.684479 30.9116C0.684479 33.646 2.935 35.8626 5.7112 35.8626C8.48739 35.8626 10.7379 33.646 10.7379 30.9116C10.7379 28.1772 8.48739 3.21045 5.7112 3.21045Z" fill="#E8EBF7"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M10.7379 30.9116C10.7379 28.1772 8.48739 3.21045 5.7112 3.21045C2.935 3.21045 0.684479 28.1772 0.684479 30.9116C0.684479 33.646 2.935 35.8626 5.7112 35.8626C8.48739 35.8626 10.7379 33.646 10.7379 30.9116Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M5.70389 35.8624V14.9761" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M5.25488 30.3044L3.03128 28.1143" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="47" height="40" fill="white"/>
</clipPath>
</defs>
</svg>

`,
          title: "Store Delivery",
          svg1: `<svg width="37" height="37" viewBox="0 0 37 37" fill="none" xmlns="http://www.w3.org/2000/svg">
<circle cx="18.5" cy="18.5" r="18.5" fill="white"/>
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.031 20H26.111L20.439 25.743C20.136 26.017 20.437 26.478 20.721 26.771C20.869 26.923 21.068 27 21.268 27C21.452 27 21.637 26.935 21.781 26.803L29.766 19.53C29.826 19.47 29.836 19.436 29.857 19.407C29.899 19.344 29.926 19.318 29.94 19.287C29.964 19.224 29.967 19.179 29.975 19.135C29.983 19.093 29.999 19.053 30 19.01C29.999 18.946 29.983 18.906 29.975 18.864C29.966 18.819 29.964 18.775 29.947 18.733C29.926 18.681 29.899 18.656 29.881 18.626C29.836 18.562 29.826 18.529 29.8 18.502C29.77 18.476 21.782 11.197 21.782 11.197C21.481 10.923 21.007 10.936 20.722 11.229C20.438 11.521 20.137 11.982 20.439 12.257L26.111 18H7.031C6.617 18 6 18.598 6 19C6 19.401 6.617 20 7.031 20Z" fill="#283060"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="24" height="16" fill="white" transform="translate(6 11)"/>
</clipPath>
</defs>
</svg>
`,
        },
        {
          svg: `<svg width="48" height="40" viewBox="0 0 48 40" fill="none" xmlns="http://www.w3.org/2000/svg">
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M4.00003 39.5534H44.4466V4.07861H4.00003V39.5534Z" fill="#E8EBF7"/>
<path opacity="0.2" fill-rule="evenodd" clip-rule="evenodd" d="M44.6372 4.78442C44.6212 5.22254 44.6075 5.65831 44.6047 6.08842C44.6033 6.29172 44.6165 6.48231 44.6362 6.66678H3.91716V4.78442H44.6372Z" fill="#3A427C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M4.00003 39.2941H44V4H4.00003V39.2941Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M0.941162 39.2942H47.0588" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M10.6706 39.5533H37.7765V15.4851H10.6706V39.5533Z" fill="#AB651E"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M10.5883 39.2942H37.4118V13.4119H10.5883V39.2942Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M10.6706 27.6593H37.7765V11.7205H10.6706V27.6593Z" fill="#894D0F"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M10.6706 22.0121H37.7765V11.2498H10.6706V22.0121Z" fill="#E7EBF6"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M10.5883 28H37.4118V11.0588H10.5883V28Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M10.6701 14.8235H37.3054" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M10.6701 18.5881H37.3054" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M10.6701 22.353H37.3054" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M22.5883 25.1765H25.4118H22.5883Z" stroke="white" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M2.11763 4.07805H46.3289V0.705811H2.11763V4.07805Z" fill="#3A427C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M2.11763 4.47052H45.8823V0.705811H2.11763V4.47052Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="48" height="40" fill="white"/>
</clipPath>
</defs>
</svg>

`,
          title: "Store Delivery",
          svg1: `<svg width="37" height="37" viewBox="0 0 37 37" fill="none" xmlns="http://www.w3.org/2000/svg">
<circle cx="18.5" cy="18.5" r="18.5" fill="white"/>
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.031 20H26.111L20.439 25.743C20.136 26.017 20.437 26.478 20.721 26.771C20.869 26.923 21.068 27 21.268 27C21.452 27 21.637 26.935 21.781 26.803L29.766 19.53C29.826 19.47 29.836 19.436 29.857 19.407C29.899 19.344 29.926 19.318 29.94 19.287C29.964 19.224 29.967 19.179 29.975 19.135C29.983 19.093 29.999 19.053 30 19.01C29.999 18.946 29.983 18.906 29.975 18.864C29.966 18.819 29.964 18.775 29.947 18.733C29.926 18.681 29.899 18.656 29.881 18.626C29.836 18.562 29.826 18.529 29.8 18.502C29.77 18.476 21.782 11.197 21.782 11.197C21.481 10.923 21.007 10.936 20.722 11.229C20.438 11.521 20.137 11.982 20.439 12.257L26.111 18H7.031C6.617 18 6 18.598 6 19C6 19.401 6.617 20 7.031 20Z" fill="#283060"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="24" height="16" fill="white" transform="translate(6 11)"/>
</clipPath>
</defs>
</svg>
`,
        },
        {
          svg: `<svg width="47" height="40" viewBox="0 0 47 40" fill="none" xmlns="http://www.w3.org/2000/svg">
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M3.27805 39.0698H27.6293V14.8838H3.27805V39.0698Z" fill="#E7EBF6"/>
<path opacity="0.2" fill-rule="evenodd" clip-rule="evenodd" d="M27.7492 20.9303H3.62646C3.17549 20.9303 2.80975 20.514 2.80975 20.0001C2.80975 19.4861 3.17549 19.0698 3.62646 19.0698H27.7492C28.2001 19.0698 28.5659 19.4861 28.5659 20.0001C28.5659 20.514 28.2001 20.9303 27.7492 20.9303Z" fill="#3A427C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M3.51221 39.3022H27.8634V19.3022H3.51221V39.3022Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M2.57562 19.3022H28.3317V15.5813H2.57562V19.3022Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M18.4044 24.6357C18.4044 24.6357 22.3231 20.205 23.2831 16.0236C24.2431 11.8422 22.8766 11.2134 20.5838 10.7846C18.2906 10.3562 16.8988 10.0576 17.3217 8.58176C17.7446 7.10595 20.5838 5.74548 20.5838 5.74548C20.5838 5.74548 18.9593 4.08921 21.4122 2.77897C23.8647 1.46827 25.4072 0.998042 27.478 0.932461C29.5493 0.866414 30.0007 2.24409 28.705 3.50967C27.4092 4.77479 25.9542 9.17525 29.642 11.6032C33.3293 14.0311 40.3284 16.9836 42.3182 20.1799C44.308 23.3762 45.3279 24.725 45.4122 30.2799C45.4961 35.8348 44.2532 39.4301 38.1092 39.4301H27.478C27.478 39.4301 20.3417 39.0576 20.3417 33.1608" fill="#AB651E"/>
<path d="M20.5838 35.4536C20.5838 35.4536 21.8866 39.3024 28.3757 39.3024H39.145C39.145 39.3024 45.4272 39.3987 45.4272 32.3364C45.4272 25.274 45.2202 20.5429 36.5217 15.8122C27.8236 11.081 27.8236 10.3954 27.8236 7.10426C27.8236 3.8131 29.5493 2.44194 29.5493 2.44194C29.5493 2.44194 28.652 0.384727 25.2695 1.07031C21.8866 1.75589 19.1944 4.15589 20.2991 5.45868C21.4033 6.76147 26.6501 9.09403 26.2356 15.1271" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M20.0471 5.91162C20.0471 5.91162 16.985 7.69441 17.0543 9.27116C17.1231 10.8484 22.8527 9.68278 23.5434 12.6995C24.2337 15.7163 19.1518 24.4014 19.1518 24.4014" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M23.5434 12.6994C23.5434 12.6994 24.0637 10.3236 28.7049 10.0371" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M0.936584 39.3022H45.8927" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M11.239 38.6047H33.7171V23.7209H11.239V38.6047Z" fill="white"/>
<path opacity="0.2" fill-rule="evenodd" clip-rule="evenodd" d="M33.1317 29.7674H11.8244C11.5008 29.7674 11.239 29.4549 11.239 29.0693C11.239 28.6846 11.5008 28.3721 11.8244 28.3721H33.1317C33.4553 28.3721 33.7171 28.6846 33.7171 29.0693C33.7171 29.4549 33.4553 29.7674 33.1317 29.7674Z" fill="#3A427C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M11.9415 39.3024H33.0146V28.1396H11.9415V39.3024Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M11.0049 28.1396H34.4195V24.4187H11.0049V28.1396Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M25.4274 31.4785C24.7296 30.7855 23.5987 30.7855 22.9014 31.4785L22.6818 31.6966L22.4621 31.4785C21.7644 30.7855 20.6334 30.7855 19.9362 31.4785C19.2384 32.1715 19.2384 33.2948 19.9362 33.9873L20.1558 34.2055L22.1858 36.2218C22.4598 36.4939 22.9037 36.4939 23.1777 36.2218L25.2077 34.2055L25.4274 33.9873C26.1251 33.2948 26.1251 32.1715 25.4274 31.4785Z" fill="#AB651E"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="46.8293" height="40" fill="white"/>
</clipPath>
</defs>
</svg>

`,
          title: "Store Delivery",
          svg1: `<svg width="37" height="37" viewBox="0 0 37 37" fill="none" xmlns="http://www.w3.org/2000/svg">
<circle cx="18.5" cy="18.5" r="18.5" fill="white"/>
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.031 20H26.111L20.439 25.743C20.136 26.017 20.437 26.478 20.721 26.771C20.869 26.923 21.068 27 21.268 27C21.452 27 21.637 26.935 21.781 26.803L29.766 19.53C29.826 19.47 29.836 19.436 29.857 19.407C29.899 19.344 29.926 19.318 29.94 19.287C29.964 19.224 29.967 19.179 29.975 19.135C29.983 19.093 29.999 19.053 30 19.01C29.999 18.946 29.983 18.906 29.975 18.864C29.966 18.819 29.964 18.775 29.947 18.733C29.926 18.681 29.899 18.656 29.881 18.626C29.836 18.562 29.826 18.529 29.8 18.502C29.77 18.476 21.782 11.197 21.782 11.197C21.481 10.923 21.007 10.936 20.722 11.229C20.438 11.521 20.137 11.982 20.439 12.257L26.111 18H7.031C6.617 18 6 18.598 6 19C6 19.401 6.617 20 7.031 20Z" fill="#283060"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="24" height="16" fill="white" transform="translate(6 11)"/>
</clipPath>
</defs>
</svg>
`,
        },
        {
          svg: `<svg width="44" height="40" viewBox="0 0 44 40" fill="none" xmlns="http://www.w3.org/2000/svg">
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M40.9085 7.91211H3.72293C2.6347 7.91211 1.75238 8.79738 1.75238 9.88925V34.8914C1.75238 35.9833 2.6347 36.8686 3.72293 36.8686H40.9085C41.9967 36.8686 42.879 35.9833 42.879 34.8914V9.88925C42.879 8.79738 41.9967 7.91211 40.9085 7.91211Z" fill="white"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M30.6973 11.8017C31.9441 19.0276 31.9441 26.2535 30.6973 33.479C22.3832 34.5634 14.0681 34.5634 5.75394 33.479C4.50756 26.2535 4.50756 19.0276 5.75394 11.8017C14.0681 10.7181 22.3832 10.7181 30.6973 11.8017Z" fill="#AB651E"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M30.6973 11.8017C22.3832 10.7181 14.0681 10.7181 5.75394 11.8017C4.50756 19.0276 4.50756 26.2535 5.75394 33.479C14.0681 34.5634 22.3832 34.5634 30.6973 33.479C31.9441 26.2535 31.9441 19.0276 30.6973 11.8017Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M40.9085 7.91211H3.72293C2.6347 7.91211 1.75238 8.79738 1.75238 9.88925V34.8914C1.75238 35.9833 2.6347 36.8686 3.72293 36.8686H40.9085C41.9967 36.8686 42.879 35.9833 42.879 34.8914V9.88925C42.879 8.79738 41.9967 7.91211 40.9085 7.91211Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.27063 39.2317H3.94286L3.50476 36.9231H7.70872L7.27063 39.2317Z" fill="#D6D7E0"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.27063 39.2317H3.94286L3.50476 36.9231H7.70872L7.27063 39.2317Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M0.87619 39.3406H42.9333" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M41.004 39.2317H37.6762L37.2381 36.9231H41.4421L41.004 39.2317Z" fill="#D6D7E0"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M41.004 39.2317H37.6762L37.2381 36.9231H41.4421L41.004 39.2317Z" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M35.0476 33.5322H39.2919V26.3735H35.0476V33.5322Z" stroke="#1C1F34" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M39.2919 20.5907C39.2919 19.4148 38.3417 18.4614 37.1698 18.4614C35.9979 18.4614 35.0476 19.4148 35.0476 20.5907C35.0476 21.7665 35.9979 22.7199 37.1698 22.7199C38.3417 22.7199 39.2919 21.7665 39.2919 20.5907Z" stroke="#1C1F34" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M39.2919 13.9974C39.2919 12.8216 38.3417 11.8682 37.1698 11.8682C35.9979 11.8682 35.0476 12.8216 35.0476 13.9974C35.0476 15.1732 35.9979 16.1266 37.1698 16.1266C38.3417 16.1266 39.2919 15.1732 39.2919 13.9974Z" stroke="#1C1F34" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M20.9453 11.4285V14.0302L19.2762 16.6395L20.1108 18.4812V21.0126L22.3503 22.7397L23.7277 18.4812L26.4425 17.6021" stroke="#1C1F34" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M31.4176 19.7803L27.7078 20.6172L25.7604 22.7464H22.3429L23.9056 26.0409L27.3372 27.3469L26.4351 30.3091L27.8007 33.4484" stroke="#1C1F34" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M24.4549 26.1515L26.3098 22.4175L22.3429 22.6575L24.4549 26.1515Z" fill="#1C1F34"/>
<path d="M12.2487 33.4695L11.8106 31.1231L10.9524 30.7693" stroke="#1C1F34" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M26.5065 11.8682L25.8476 12.9363" stroke="#1C1F34" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
<path d="M23.6571 6.08486L28.3969 0.87915" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M29.1846 1.01495C29.1846 0.454506 28.7316 0 28.173 0C27.6145 0 27.1619 0.454506 27.1619 1.01495C27.1619 1.57538 27.6145 2.02989 28.173 2.02989C28.7316 2.02989 29.1846 1.57538 29.1846 1.01495Z" fill="#1C1F34"/>
<path d="M21.3874 6.08486L16.6476 0.87915" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M15.7714 1.01495C15.7714 0.454506 16.2244 0 16.783 0C17.3416 0 17.7941 0.454506 17.7941 1.01495C17.7941 1.57538 17.3416 2.02989 16.783 2.02989C16.2244 2.02989 15.7714 1.57538 15.7714 1.01495Z" fill="#1C1F34"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M24.8899 7.21194C24.8899 6.38469 23.8293 5.71436 22.5212 5.71436C21.213 5.71436 20.1524 6.38469 20.1524 7.21194" fill="white"/>
<path d="M24.8899 7.6515C24.8899 6.58161 23.8293 5.71436 22.5212 5.71436C21.213 5.71436 20.1524 6.58161 20.1524 7.6515" stroke="#1C1F34" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="43.8095" height="40" fill="white"/>
</clipPath>
</defs>
</svg>
`,
          title: "Store Delivery",
          svg1: `<svg width="37" height="37" viewBox="0 0 37 37" fill="none" xmlns="http://www.w3.org/2000/svg">
<circle cx="18.5" cy="18.5" r="18.5" fill="white"/>
<g clip-path="url(#clip0)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M7.031 20H26.111L20.439 25.743C20.136 26.017 20.437 26.478 20.721 26.771C20.869 26.923 21.068 27 21.268 27C21.452 27 21.637 26.935 21.781 26.803L29.766 19.53C29.826 19.47 29.836 19.436 29.857 19.407C29.899 19.344 29.926 19.318 29.94 19.287C29.964 19.224 29.967 19.179 29.975 19.135C29.983 19.093 29.999 19.053 30 19.01C29.999 18.946 29.983 18.906 29.975 18.864C29.966 18.819 29.964 18.775 29.947 18.733C29.926 18.681 29.899 18.656 29.881 18.626C29.836 18.562 29.826 18.529 29.8 18.502C29.77 18.476 21.782 11.197 21.782 11.197C21.481 10.923 21.007 10.936 20.722 11.229C20.438 11.521 20.137 11.982 20.439 12.257L26.111 18H7.031C6.617 18 6 18.598 6 19C6 19.401 6.617 20 7.031 20Z" fill="#283060"/>
</g>
<defs>
<clipPath id="clip0">
<rect width="24" height="16" fill="white" transform="translate(6 11)"/>
</clipPath>
</defs>
</svg>
`,
        },
      ],
    };
  },
  methods: {
    gotoAddress() {
      this.$router.push({ path: "/about/2" });
      // console.log(this.$route);
    },
  },
};
</script>

<style lang="scss" scoped>
.main_cards {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  font-family: "Nunito", sans-serif;
  @media (max-width: 760px) {
    margin-bottom: 20px;
  }
  .main_card {
    flex: 0 0 calc(50% - 3px);
    max-width: calc(50% - 3px);
    width: 100%;
    background: #f27f0b;
    margin-top: 5px;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 5px 0;
    @media (max-width: 560px) {
      max-width: 100%;
      flex: 0 0 100%;
    }
    h4 {
      margin: 15px 0;
      font-style: normal;
      font-weight: bold;
      font-size: 21px;
      line-height: 29px;

      color: #ffffff;
    }
    span {
      cursor: pointer;
    }
  }
}
</style>