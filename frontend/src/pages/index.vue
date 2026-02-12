
<template>
  <DefaultLayout>
    <v-row>
      <v-col cols="12">
        <v-card 
          elevation="2" 
          rounded="lg" 
          class="pa-4"
        >
          <v-card-item>
            <v-card-title class="text-h4 font-weight-bold">
              ยินดีต้อนรับ! 👋
            </v-card-title>
            <v-card-subtitle class="text-subtitle-1 mt-2">
              เริ่มเพิ่มข้อมูลใหม่ได้เลยครับ
            </v-card-subtitle>
          </v-card-item>

          <v-card-text class="mt-4">
            <p class="text-grey-darken-1">ยังไม่มีข้อมูลในลิสต์ตอนนี้...</p>
          </v-card-text>

          <v-card-actions>
           <v-btn 
            color="primary" 
            variant="elevated" 
            to="/create" 
          >
            เพิ่มข้อมูลใหม่
          </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </DefaultLayout>
</template>