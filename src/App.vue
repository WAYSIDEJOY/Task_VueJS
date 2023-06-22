<template>
  <div class="container mt-4">
        <form @submit.prevent="registerUser" novalidate>
            <div v-show="step === 1" class="step">
              <div class="mb-3">
                <label for="name" class="form-label">Ваше имя</label>
                <input v-model="formReg.name" type="text" class="form-control" id="name" aria-describedby="emailHelp">
              </div>

              <div class="mb-3">
                <label for="surname" class="form-label">Ваша фамилия</label>
                <input v-model="formReg.surname" type="text" class="form-control" id="exampleInputPassword1">
              </div>

              <div class="mb-3">
                <label for="email" class="form-label">Email</label>
                <input v-model="formReg.email" type="text" class="form-control" id="exampleInputPassword1">
              </div>

              <button @click="nextStep" type="button" class="btn btn-primary">Следующий шаг</button>
            </div>

              <div v-show="step === 2" class="step">
                <div class="mb-3">
                  <label for="password" class="form-label">Введите пароль</label>
                  <input v-model="formReg.password" type="password" class="form-control" id="password" aria-describedby="emailHelp">
                </div>

                <div class="mb-3">
                  <label for="passwordConfirm" class="form-label">Повтоврно введите пароль</label>
                  <input v-model="formReg.passwordConfirm" type="password" class="form-control" id="passwordConfirm">
                </div>

                <button @click="backStep" type="button" class="btn btn-secondary">Назад</button>
                <button type="submit" class="btn btn-primary">Зарегестрироваться</button>

              </div>
        </form>
  </div>
</template>

<script>
export default {
    data() {
      return {
        step: 1,
        formReg: {
          name: '',
          surname: '',
          email: '',
          password: '',
          passwordConfirm: ''
        }

        
        
      }
    },
    methods: {
      nextStep() {
          this.step++
      },
      backStep() {
        this.step--
      },
      registerUser() {
        console.log('Регистрация прошла успешно')
        console.log(this.formReg.name)
        console.log(this.formReg.surname)
        console.log(this.formReg.email)
        console.log(this.formReg.password)
        console.log(this.formReg.passwordConfirm)
      }
    }

    
    
 
  }
</script>

<style>

</style>
