<script setup>
const state = reactive({
  email: undefined,
  password: undefined
})

const validate = (state) => {
  const errors = []
  if (!state.email) errors.push({ path: 'email', message: 'Required' })
  if (!state.password) errors.push({ path: 'password', message: 'Required' })
  return errors
}

async function onLogin(event) {
  // Do something with data
  console.log(event.data)
}

async function onRegister(event) {
  // Do something with data
  console.log(event.data)
}

const items = [{
  slot: 'login',
  label: 'Login'
},{
  slot: 'register',
  label: 'Register'
},
]

</script>

<template>
  <UModal>
    <div class="p-4">
      <UTabs :items="items" class="w-full">
        <template #login="{ item }">
          <UCard>
            <template #header>
              <p class="text-base font-semibold leading-6 text-gray-900 dark:text-white">
                {{ item.label }}
              </p>
              
            </template>

            <UForm :validate="validate" :state="state" class="space-y-4" @submit="onLogin">
              <UFormGroup label="Email" name="email">
                <UInput v-model="state.email" />
              </UFormGroup>

              <UFormGroup label="Password" name="password">
                <UInput v-model="state.password" type="password" />
              </UFormGroup>

              <UButton type="submit">
                Submit
              </UButton>
            </UForm>
          </UCard>
        </template>

        <template #register="{ item }">
          <UCard>
            <template #header>
              <h3 class="text-base font-semibold leading-6 text-gray-900 dark:text-white">
                {{ item.label }}
              </h3>
              
            </template>

            <UForm :validate="validate" :state="state" class="space-y-4" @submit="onRegister">
              <UFormGroup label="Email" name="email">
                <UInput v-model="state.email" />
              </UFormGroup>

              <UFormGroup label="Password" name="password">
                <UInput v-model="state.password" type="password" />
              </UFormGroup>

              <UButton type="submit">
                Submit
              </UButton>
            </UForm>
          </UCard>
        </template>
      </UTabs>
    </div>
  </UModal>
</template>