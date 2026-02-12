
<template>
  <DefaultLayout>
    <v-row justify="center">
      <v-col cols="12" md="8" lg="6">
        <v-card variant="flat" border class="pa-6 rounded-lg">
          <v-card-item>
            <v-card-title class="text-h4 font-weight-bold">
              ยินดีต้อนรับ! 
            </v-card-title>
            <v-card-subtitle class="text-subtitle-1 mt-2">
              เริ่มเพิ่มข้อมูลงานใหม่ได้เลย
            </v-card-subtitle>
          </v-card-item>
          <v-card-actions>
           <v-btn 
              color="primary" 
              variant="elevated" 
              block
              prepend-icon="mdi-plus"
              @click="goToCreate"
          >
            เพิ่มข้อมูลใหม่
          </v-btn>
          </v-card-actions>
           <v-card-actions>
           <v-btn 
           color="secondary" 
              variant="tonal" 
              block
              prepend-icon="mdi-format-list-bulleted"
              @click="goToList"
          >
            ข้อมูลของคุณ
          </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </DefaultLayout>
</template>

<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const goToCreate = () => {
  router.push('/create')
}
const goToList = () => {
  router.push('/list')
}
</script>