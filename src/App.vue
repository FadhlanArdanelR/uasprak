<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar class="custom-toolbar">
        <div class="toolbar-left">
          <q-btn-dropdown class="custom-dropdown" label="MENU" dropdown-icon="">
            <q-list class="nav-list">
              <q-item clickable v-close-popup>
                <router-link to="/">
                  <q-item-section>
                    <q-item-label class="nav-label">Weather</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
              <q-item clickable v-close-popup>
                <router-link to="/tugas1">
                  <q-item-section>
                    <q-item-label class="nav-label">TUGAS 1</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
              <q-item clickable v-close-popup>
                <router-link to="/tugas2">
                  <q-item-section>
                    <q-item-label class="nav-label">TUGAS 2</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
              <q-item clickable v-close-popup>
                <router-link to="/tugas3">
                  <q-item-section>
                    <q-item-label class="nav-label">TUGAS 3</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
              <q-item clickable v-close-popup>
                <router-link to="/tugas4">
                  <q-item-section>
                    <q-item-label class="nav-label">TUGAS 4</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
              <q-item clickable v-close-popup>
                <router-link to="/tugas5">
                  <q-item-section>
                    <q-item-label class="nav-label">TUGAS 5</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
              <q-item clickable v-close-popup>
                <router-link to="/tugas6">
                  <q-item-section>
                    <q-item-label class="nav-label">TUGAS 6</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
              <q-item clickable v-close-popup>
                <router-link to="/tugas7">
                  <q-item-section>
                    <q-item-label class="nav-label">TUGAS 7</q-item-label>
                  </q-item-section>
                </router-link>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'App',
  setup() {},
};
</script>

<style>
.custom-toolbar {
  background-color: white;
  color: black;
  text-decoration: none;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.toolbar-left {
  display: flex;
  align-items: center;
}

.toolbar-right {
  display: flex;
  align-items: center;
}

.toolbar-spacer {
  flex: 1;
}

.nav-link {
  margin: 0 20px;
  color: var(--light-beige);
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s, transform 0.3s;
}

.nav-link:hover {
  color: var(--beige);
  transform: scale(1.1);
}

.nav-link:active {
  transform: scale(0.9);
}

.custom-dropdown {
  background-color: var(--medium-red);
  color: var(--light-beige);
}

.nav-list {
  background-color: var(--dark-red);
  color: var(--light-beige);
}

.q-item-section {
  color: var(--beige) !important;
}

.nav-label {
  font-weight: bold;
  color: black !important;
}

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  background-color: #686D76;
  background-size: 400% 400%;
  animation: gradientAnimation 20s ease infinite;
}

.q-layout, .q-page-container {
  background: transparent;
}
</style>
