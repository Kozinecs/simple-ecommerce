<template>
  <div class="card">
    <Menubar :model="items">
      <template #start>
        <img alt="logo" src="../assets/vue.svg" />
      </template>
      <template #end>
        <Button label="Login" icon="pi pi-sign-in" @click="showModal = true" />

        <Dialog
          v-model="showModal"
          header="Login"
          :visible="showModal"
          @hide="showModal = false"
        >
          <div class="p-fluid">
            <div class="flex flex-column gap-2">
              <label for="username">Username</label>
              <InputText id="username" v-model="username" />
            </div>
            <div class="p-field">
              <label for="password">Password</label>
              <Password id="password" v-model="password" />
            </div>
          </div>
          <div class="p-d-flex p-jc-end">
            <Button label="Login" icon="pi pi-sign-in" @click="login" />
          </div>
        </Dialog>
      </template>
    </Menubar>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const items = ref([
  {
    label: 'Home',
    icon: 'pi pi-home',
  },
  {
    label: 'Features',
    icon: 'pi pi-star',
  },
  {
    label: 'Projects',
    icon: 'pi pi-search',
    items: [
      {
        label: 'Components',
        icon: 'pi pi-bolt',
      },
      {
        label: 'Blocks',
        icon: 'pi pi-server',
      },
      {
        label: 'UI Kit',
        icon: 'pi pi-pencil',
      },
      {
        label: 'Templates',
        icon: 'pi pi-palette',
        items: [
          {
            label: 'Apollo',
            icon: 'pi pi-palette',
          },
          {
            label: 'Ultima',
            icon: 'pi pi-palette',
          },
        ],
      },
    ],
  },
  {
    label: 'Contact',
    icon: 'pi pi-envelope',
  },
])

const showModal = ref(false)
const username = ref('')
const password = ref('')

const login = () => {
  // Perform login logic here
}
</script>
