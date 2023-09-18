<template>
    <div id="home-view">
      <!-- Include your top navigation bars here -->
      <div class="navbars">
        <TopTopNavbar />
        <TopNavbar />
  
        <!-- Main navigation -->
        <MainNavbar />
      </div>
  
      <!-- Product categories -->
      <ImageNavbar />
  
      <!-- Product Gallery Component -->
      <ProductGallery :products="productData" />
  
      <!-- Air Conditioner List Component -->
      <AirConditionerList id="airconditionerSection" :airConditionerProducts="airConditionerData" />
      <!-- Refrigerator List Component -->
      <RefrigeratorList id="refrigeratorSection" :refrigeratorProducts="refrigeratorData" />
  
      <!-- Audio Video List Component -->
      <AudioVideoList id="audiovideoSection" :audioVideoProducts="audioVideoData" />
  
      <!-- Smart Phone List Component -->
      <SmartPhoneList id="smartphoneSection" :smartPhoneProducts="smartPhoneData" />
  
      <!-- Kitchen Appliances List Component -->
      <KitchenAppliancesList id="kitchenappliancesSection" :kitchenAppliancesProducts="kitchenAppliancesData" />
  
      <!-- Home Appliances List Component -->
      <HomeAppliancesList id="homeappliancesSection" :homeAppliancesProducts="homeAppliancesData" />
  
      <!-- PCs & Laptop List Component -->
      <PcsLaptopList id="pcs&laptopSection" :pcsLaptopProducts="pcsLaptopData" />
  
      <SmartHomeList id="smarthomeSection" :smartHomeProducts="SmarthomeData" />
      <ContactInfo />
      <!-- Add your other components here -->
    </div>
  </template>
  
  <script>
  import { ref, computed } from 'vue';
  import TopTopNavbar from '@/components/TopTopNavbar.vue';
  import TopNavbar from '@/components/TopNavbar.vue';
  import MainNavbar from '@/components/MainNavbar.vue';
  import ImageNavbar from '@/components/ImageNavbar.vue';
  import ProductGallery from '@/components/ProductGallery.vue';
  import AirConditionerList from '@/components/AirConditionerList.vue';
  import RefrigeratorList from '@/components/RefrigeratorList.vue';
  import AudioVideoList from '@/components/AudioVideoList.vue';
  import SmartPhoneList from '@/components/SmartPhoneList.vue';
  import SmartHomeList from '@/components/SmartHomeList.vue';
  import ContactInfo from '@/components/ContactInfo.vue';
  import KitchenAppliancesList from '@/components/KitchenAppliancesList.vue';
  import HomeAppliancesList from '@/components/HomeAppliancesList.vue';
  import PcsLaptopList from '@/components/PcsLaptopList.vue';
  import dbData from '@/data/db.json';
  
  export default {
    name: 'HomeView',
    components: {
      TopTopNavbar,
      TopNavbar,
      MainNavbar,
      ImageNavbar,
      ProductGallery,
      AirConditionerList,
      RefrigeratorList,
      AudioVideoList,
      SmartPhoneList,
      KitchenAppliancesList,
      HomeAppliancesList,
      PcsLaptopList,
      SmartHomeList,
      ContactInfo
    },
    setup() {
      const productData = ref([
        { title: 'airConditioner', data: dbData.AirConditioner, image: require('@/assets/air_conditioner.jpg') },
        { title: 'Refrigerator', data: dbData.Refrigerator, image: require('@/assets/refrigrator.jpg') },
        { title: 'audioVideo', data: dbData.Audiovideo, image: require('@/assets/audio_video.jpg') },
        { title: 'smartPhone', data: dbData.Smartphone, image: require('@/assets/smart_phone.jpg') },
        { title: 'kitchenAppliances', data: dbData.Kitchenappliances, image: require('@/assets/kitchen_appliances.jpg') },
        { title: 'homeAppliances', data: dbData.Homeappliances, image: require('@/assets/home_appliances.jpg') },
        { title: 'pcs&laptop', data: dbData.PCslaptop, image: require('@/assets/pc_laptop.jpg') },
        { title: 'Smarthome', data: dbData.Smarthome, image: require('@/assets/smart_home.jpg') }
    ]);
  
      // Extract data for each product category
      const airConditionerData = computed(() => productData.value.find(item => item.title === 'airConditioner').data);
      const refrigeratorData = computed(() => productData.value.find(item => item.title === 'Refrigerator').data);
      const audioVideoData = computed(() => productData.value.find(item => item.title === 'audioVideo').data);
      const smartPhoneData = computed(() => productData.value.find(item => item.title === 'smartPhone').data);
      const kitchenAppliancesData = computed(() => productData.value.find(item => item.title === 'kitchenAppliances').data);
      const homeAppliancesData = computed(() => productData.value.find(item => item.title === 'homeAppliances').data);
      const pcsLaptopData = computed(() => productData.value.find(item => item.title === 'pcs&laptop').data);
      const SmarthomeData = computed(() => productData.value.find(item => item.title === 'Smarthome').data);
  
      return {
        productData,
        airConditionerData,
        refrigeratorData,
        audioVideoData,
        smartPhoneData,
        kitchenAppliancesData,
        homeAppliancesData,
        pcsLaptopData,
        SmarthomeData
      };
    },
  };
  </script>
  
  <style scoped>
  .navbars {
    width: 102%;
    position: relative;
    left: -2ch;
    height: 300%;
    top: -1ch;
  }
  
  #home-view {
    background-color: rgb(232, 229, 229);
    /* Change background color here */
    /* Add other global styles for your app container */
  }
  </style>
  