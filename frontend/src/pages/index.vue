
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
            to="/create" 
          >
            เพิ่มข้อมูลใหม่
          </v-btn>
          </v-card-actions>
           <v-card-actions>
           <v-btn 
            color="primary" 
            variant="elevated" 
            to="/list" 
          >
            ข้อมูลของคุณ
          </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </DefaultLayout>
</template>