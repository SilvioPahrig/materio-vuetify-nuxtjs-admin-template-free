<template>
  <VList>
    <VListItem to="/account-settings">
      <template #prepend>
        <VIcon
          class="me-2"
          icon="ri-user-line"
          size="22"
        />
      </template>
      <VListItemTitle>Profile</VListItemTitle>
    </VListItem>
    <!-- Divider -->
    <VDivider class="my-2"/>
    <VListItem link>
      <template #prepend>
        <VIcon
          class="me-2"
          icon="ri-user-settings-line"
          size="22"
        />
      </template>
      <VListItemTitle>Admin-Backend</VListItemTitle>
    </VListItem>
    <VListItem link>
      <template #prepend>
        <VIcon
          class="me-2"
          icon="ri-smartphone-line"
          size="22"
        />
      </template>

      <VListItemTitle>App-Backend</VListItemTitle>
    </VListItem>
    <VListItem link>
      <template #prepend>
        <VIcon
          class="me-2"
          size="22"
        />
      </template>
      <VListItemTitle>apothekeplus.de</VListItemTitle>
    </VListItem>
    <VListItem link>
      <template #prepend>
        <VIcon
          class="me-2"
          size="22"
        />
      </template>
      <VListItemTitle>Apothekenjobs</VListItemTitle>
    </VListItem>
    <VListItem link>
      <template #prepend>
        <VIcon
          class="me-2"
          icon="ri-flag-line"
          size="22"
        />
      </template>
      <VListItemTitle>WKZ/Industriewerbund</VListItemTitle>
    </VListItem>

    <!-- Divider -->
    <VDivider class="my-2"/>

    <VListItem link>
      <template #prepend>
        <VIcon
          class="me-2"
          icon="ri-information-line"
          size="22"
        />
      </template>
      <VListItemTitle>Impressum</VListItemTitle>
    </VListItem>

    <!-- Divider -->
    <VDivider class="my-2"/>
    <!-- 👉 Logout -->
    <VListItem to="/login">
      <template #prepend>
        <VIcon
          class="me-2"
          icon="ri-logout-box-r-line"
          size="22"
        />
      </template>

      <VListItemTitle>Logout</VListItemTitle>
    </VListItem>
  </VList>
</template>
<script setup>
</script>
