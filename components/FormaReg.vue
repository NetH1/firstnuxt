<template>
  <div class="bg-black">
    <div class="container mx-auto p-16">
      <div class="flex items-start justify-between bg-white p-16 rounded-2xl">
        <div class="w-1/2">
          <h1>Поможем в выборе!</h1>
          <p>Если у вас есть вопросы о формате или вы не знаете, что выбрать, оставьте свой номер — мы позвоним, чтобы ответить на все ваши вопросы.</p>
        </div>
        <div class="w-1/2">
          <div>
            <input class="w-full p-2 rounded-lg bg-gray-200 border border-gray-400 text-lg text-black" v-model="form.name" placeholder="Имя" type="text">
          </div>
          <div class="flex mt-3">
            <input class="w-full p-2 rounded-lg bg-gray-200 border border-gray-400 text-lg text-black mr-2" v-model="form.phone" placeholder="Телефон" type="text">
            <input class="w-full p-2 rounded-lg bg-gray-200 border border-gray-400 text-lg text-black ml-2" v-model="form.mail" placeholder="Электронная почта" type="text">
          </div>
          <div class="flex justify-between mt-3">
            <p class="mb-0 text-xs w-3/4">Нажимая на кнопку, я соглашаюсь на обработку персональных данных и с правилами пользования Платформой</p>
            <button @click="addTodo()" class="w-1/2 bg-blue-500 text-white font-bold text-center rounded-2xl">Отправить</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'FormaReg',
  data () {
    return {
      form: {
        name: '',
        phone: '',
        mail: ''
      }
    }
  },
  methods: {
    async addTodo () {
      await axios.post('http://localhost:3001/todos', { name: this.form.name, mail: this.form.mail, phone: this.form.phone })
    }
  }
}
</script>
