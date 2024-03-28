<template>
  <div>
    <h4>Thêm mới liên hệ</h4>
    <ContactForm :contact="{}" @submit:contact="addContact" />
    <p>{{ message }}</p>
  </div>
</template>

<script>
import ContactForm from '@/components/ContactForm.vue';
import ContactService from "@/services/contact.service";

export default {
  components: {
    ContactForm,
  },
  data() {
    return {
      message: "",
    };
  },
  methods: {
    async addContact(data) {
      try {
        await ContactService.create(data);
        this.message = "Liên hệ đã được thêm mới thành công";
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
