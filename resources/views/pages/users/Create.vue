<template layout="default">

    <h1 class="text-4xl text-center text-black-900">Create User</h1>
    <hr>

    <div class="max-w-md mx-auto mt-5 ">
        <form @submit.prevent="submit" class="bg-gray-400 shadow-md rounded px-8 pt-6 pb-8 mb-4">
            <div clas="mb-3">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="username">User Name</label>
                <input v-model="form.username" type="text" class="field" id="username">
                <div class="text-sm text-red-500 italic" v-if="form.errors.username">{{ form.errors.username }}</div>
            </div>
            <div clas="mb-3">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="password">Password</label>
                <input v-model="form.password" type="password" class="field" id="password">
                <div class="text-sm text-red-500 italic" v-if="form.errors.password">{{ form.errors.password }}</div>
            </div>
            <div class="mb-3">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="fullname">Full Name</label>
                <input v-model="form.fullname" type="text" class="field" id="fullname">
                <div class="text-sm text-red-500 italic" v-if="form.errors.fullname">{{ form.errors.fullname }}</div>
            </div>
            <div class="mb-3">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="designation">Designation</label>
                <input v-model="form.designation" type="text" class="field" id="designation">
                <div class="text-sm text-red-500 italic" v-if="form.errors.designation">{{ form.errors.designation }}</div>
            </div>
            <div class="mb-3">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="department">Department</label>
                <input v-model="form.department" type="text" class="field" id="department">
                <div class="text-sm text-red-500 italic" v-if="form.errors.department">{{ form.errors.department }}</div>
            </div>
            <div>
                <button class="bg-blue-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded focus:shadow-outline" type="submit">
                    Create User
                </button>
            </div>
        </form>
    </div>

</template>

<script setup>
import { useForm } from '@inertiajs/inertia-vue3'
let form = useForm({
    username:'',
    password:'',
    fullname:'',
    designation:'',
    department:''
})
const submit = () => {
    form.post('/users')
}
</script>
