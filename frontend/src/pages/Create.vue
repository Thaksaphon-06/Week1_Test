<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import axios from 'axios'

const router = useRouter()

const formData = ref({
  title: '',
  description: '',
  category: 'ทั่วไป'
}) 

const saveData = async () => {
  try {

      const response = await axios.post('http://localhost:5000/projects', formData.value);
    if (response.status === 201 || response.status === 200) {
      alert('บันทึกข้อมูลสำเร็จ!');
      formData.value = { title: '', description: '', category: 'ทั่วไป' };
      router.push('/');  //กลับไปหน้าแรก
    }
  } catch (error) {
    console.error('Error:', error);
    alert('บันทึกไม่สำเร็จ!');
  }
}
</script>

<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="12" md="8" lg="6">
        
        <div class="mb-6 mt-4">
          <h1 class="text-h4 font-weight-bold">เพิ่มข้อมูลใหม่</h1>
          <p class="text-subtitle-1 text-grey-darken-1">กรอกรายละเอียดโปรเจกต์ที่คุณต้องการ</p>
        </div>

        <v-card variant="flat" border class="pa-6 rounded-lg">
          <v-form @submit.prevent="saveData">
            
            <v-text-field
              v-model="formData.title"
              label="หัวข้องานของคุณ"
              placeholder="เช่น โปรเจค Vue.js"
              variant="outlined"
              prepend-inner-icon="mdi-format-title"
              class="mb-2"
              required
            ></v-text-field>

            <v-textarea
              v-model="formData.description"
              label="รายละเอียดเพิ่มเติม"
              placeholder="ใส่รายละเอียดที่นี่..."
              variant="outlined"
              prepend-inner-icon="mdi-text"
              rows="3"
              class="mb-2"
            ></v-textarea>

            <v-select
              v-model="formData.category"
              :items="['ทั่วไป', 'งานด่วน', 'ส่วนตัว']"
              label="หมวดหมู่"
              variant="outlined"
              prepend-inner-icon="mdi-tag-outline"
              class="mb-4"
            ></v-select>

            <div class="d-flex align-center mt-4">
              <v-btn 
                color="success" 
                type="submit" 
                size="large"
                variant="elevated"
                elevation="2"
                prepend-icon="mdi-check"
              >
                บันทึกข้อมูล
              </v-btn>
              
              <v-btn 
                variant="text" 
                to="/"
                class="ml-4"
              >
                ยกเลิก
              </v-btn>
            </div>

          </v-form>
        </v-card>

      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>

</style>