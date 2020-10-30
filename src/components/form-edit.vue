<template>
    <div style="position: relative;" class="edit-container">
        
        <!-- Edit name -->
        <div class="form__input" :class="{'hide': !editData.editName}">
            <form>
                <label>Tên: </label>
                <input type="text" v-model="inputname">
                <button @click.prevent="changeData('editName',inputname)">OK</button>
            </form>
        </div>

        <!-- Edit job -->
        <div class="form__input" :class="{'hide': !editData.editJob}">
            <form>
                <label>Vị trí ứng tuyển: </label>
                <input type="text" v-model="inputname">
                <button @click.prevent="changeData('editJob', inputname)">OK</button>
            </form>
        </div>

        <!-- Edit hobby -->
        <div class="form__input" :class="{'hide': !editData.editHob}">
            <form>
                <label>Sở thích: </label>
                <input type="text" v-model="inputname">
                <button @click.prevent="changeData('editHob', inputname)">OK</button>
            </form>
        </div>

        <!-- Edit objectives -->
        <div class="form__input" :class="{'hide': !editData.editObjective}">
            <form>
                <label for="">Mục tiêu 1:</label>
                <input type="text" v-model="inputname1">
                <label for="">Mục tiêu 2:</label>
                <input type="text" v-model="inputname2">
                <button @click.prevent="changeData('editObjective', [inputname1, inputname2])">OK</button>
            </form>
        </div>

        <!-- Edit experiences -->
        <div class="form__input" :class="{'hide': !editData.editExp}">
            <form>
                <label for="">Tên công ty:</label>
                <input type="text" v-model="input1">
                <label for="">Vị trí:</label>
                <input type="text" v-model="input2">
                <label for="">Mô tả công việc:</label>
                <input type="text" v-model="input3">
                <input type="text" v-model="input4">
                <input type="text" v-model="input5">
                <input type="text" v-model="input6">
                <label for="">Thời gian:</label>
                <input type="text" v-model="input7">
                <button @click.prevent="changeData('editExp', {
                    'congty':inputname1, 
                    'vitri':inputname2,
                    'mota': [input3, input4, input5, input6],
                    'thoigian': input7})">OK</button>
            </form>
        </div>

        <!-- Edit profile -->
        <div class="form__input" :class="{'hide': !editData.editProfile}">
            <form>
                <label for="">Họ và tên:</label>
                <input type="text" v-model="input1">
                <label for="">Giới tính:</label>
                <input type="text" v-model="input2">
                <label for="">Mail:</label>
                <input type="text" v-model="input3">
                <label for="">Ngày sinh:</label>
                <input type="text" v-model="input4">
                <label for="">Điện thoại:</label>
                <input type="text" v-model="input5">
                <label for="">Địa chỉ:</label>
                <input type="text" v-model="input6">
                <button @click.prevent="changeData('editProfile', {
                    'hoten':input1, 
                    'gioitinh':input2,
                    'mail': input3,
                    'ngaysinh': input4,
                    'dienthoai': input5,
                    'diachi': input6})">OK</button>
            </form>
        </div>
        
        <form-template style="flex: 3;"></form-template>

        <div class="edit__controller">
            <button @click="editData.editName = !editData.editName">Edit Name</button>
            <button @click="editData.editJob = !editData.editJob">Edit Job</button>
            <button @click="editData.editObjective = !editData.editObjective">Edit Objectives</button>
            <button @click="editData.editExp = !editData.editExp">Edit Experience</button>
            <button @click="editData.editProfile = !editData.editProfile">Edit Profile</button>           
            <button @click="editData.editHob = !editData.editHob">Edit Hobby</button>           
        </div>

        <div style="flex: 1;">

        </div>
     
    </div>
</template>

<script>
import Form from './form-template'
import {bus} from '../main'

export default {
    components: {
        'form-template': Form,
    },
    data() {
        return {
            editData: {
                editName: false,
                editJob: false,
                editObjective: false,
                editExp: false,
                editEdu: false,
                editProfile: false,
                editSkill: false,
                editRef: false,
                editHob: false},
            input1: '',
            input2: '',
            input3: '',
            input4: '',
            input5: '',
            input6: '',
            input7: '',
            inputname1: '',
            inputname2: '',
            inputname: ''
        }
    },
    methods: {
        changeData: function (func, inputname) {
            if (inputname) {
                bus.$emit(func, inputname)
            }
            this.editData[func] = !(this.editData[func])
        },
    }
}
</script>

<style scoped>
.hide {
    display:none !important;
}

.form__input {
    position: fixed;
    top: 0;
    left: 0;

    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);

    display: flex;
    justify-content: center;
    align-items: center;
}

.form__input form {
    background-color: white;
    border: 2px solid red;
    border-radius: 10px;
    width: 40%;
    height: fit-content;
    padding: 20px;

    display: flex;
    flex-direction: column;
}

.forn__input form * {
    margin: 5px 20px;
}

.form__input input {
    margin-bottom: 20px;
    height: 30px;
}

.form__input form button {
    width: 50%;
    align-self: center;
}

.form__input label {
    display: block;
    font-weight: bold;
}

.edit-container {
    display:flex;
    position: relative; 
}

.edit__controller {
    display: flex;
    align-items: flex-start;
    flex-flow: column wrap;
    height: 100vh;

    align-items: center;
    position: fixed;
    right: 100px;
}

.edit__controller button {
    width: 100px; 
    height: 100px;
    background-color: white;
    font-weight: bold;
}

.edit__controller button:hover {
    cursor: pointer;
    background-color: var(--main-color);
}

.edit__controller button:active {
    border-width: 8px;
    background-color: var(--main-color);
}

</style>