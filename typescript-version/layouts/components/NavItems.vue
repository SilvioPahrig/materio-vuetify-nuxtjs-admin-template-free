<script lang="ts" setup>
import VerticalNavSectionTitle from '@/@layouts/components/VerticalNavSectionTitle.vue'
import VerticalNavGroup from '@layouts/components/VerticalNavGroup.vue'
import VerticalNavLink from '@layouts/components/VerticalNavLink.vue'
import serviceIcon from '@images/wave/customer-service-72.svg?raw'
</script>

<template>
  <div class="nav-wave-support-info">
    <div
      class="d-flex align-content-center align-center justify-center nav-wave-support-icon"
      v-html="serviceIcon"
    />
    <div class="text-center">
      WAVE Service-Center<br/>
      Sie haben Fragen?<br/>
      Kontaktieren Sie uns!
    </div>
    <div class="text-center text-primary">+ 49 (0)931 7801150</div>
    <div class="text-center text-primary">info@erfolg-fuer-apotheken.de</div>
  </div>

  <!-- aktuelles -->
  <VerticalNavSectionTitle
    :item="{
      heading: 'Aktuelles',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Dashboard',
      icon: 'ri-layout-masonry-line',
      to: '/dashboard',
      badgeClass: '',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Neuigkeiten',
      icon: 'ri-info-i',
      to: '/news',
      badgeClass: 'bg-error',
      badgeContent: '17',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Pinboard',
      icon: 'ri-file-search-line',
      to: '/pinboard',
      badgeClass: '',
    }"
  />

  <!-- Meine Produkte -->
  <VerticalNavSectionTitle
    :item="{
      heading: 'Meine Produkte',
    }"
  />

  <!-- orginal -->
  <VerticalNavSectionTitle
    :item="{
      heading: 'Beispiele',
    }"
  />
  <!-- 👉 Dashboards -->
    <VerticalNavLink
      :item="{
        title: 'Analytics',
        to: '/dashboard2',
      }"
    />

  <VerticalNavLink
    :item="{
      title: 'Account Settings',
      icon: 'ri-user-settings-line',
      to: '/account-settings',
    }"
  />

  <VerticalNavLink
    :item="{
      title: 'Login',
      icon: 'ri-login-box-line',
      to: '/login',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Register',
      icon: 'ri-user-add-line',
      to: '/register',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Icons',
      icon: 'ri-remixicon-line',
      to: '/icons',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Cards',
      icon: 'ri-bar-chart-box-line',
      to: '/cards',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Form Layouts',
      icon: 'ri-layout-4-line',
      to: '/form-layouts',
    }"
  />
  <VerticalNavLink
    :item="{
      title: 'Tables',
      icon: 'ri-table-alt-line',
      to: '/tables',
    }"
  />
</template>
