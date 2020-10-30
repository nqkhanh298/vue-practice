<template>
  <form-edit>    
        <!-- <button @click="editData.editName = true">Edit Job</button> -->
        <template v-slot:title>
            <form>
                <label>Tên: </label>
                <input type="text">
                <button>OK</button>
            </form>
        </template> 

        <div :class="{'hide': !editJob}" slot="job">
            <form>
                <label for="">Vị trí ứng tuyển: </label>
                <input type="text">
                <button>OK</button>
            </form>
        </div>

        <div :class="{'hide': !editObjective}" slot="objective">
            <form>
                <label for="">Mục tiêu 1:</label>
                <input type="text">
                <label for="">Mục tiêu 2:</label>
                <input type="text">
                <button>OK</button>
            </form>
        </div>

        <div :class="{'hide': !editExp}" slot="exp">
            <label for="">Tên công ty:</label>
            <input type="text">
            <label for="">Vị trí:</label>
            <input type="text">
            <label for="">Mô tả công việc:</label>
            <input type="text">
            <input type="text">
            <input type="text">
            <input type="text">
            <button>OK</button>
        </div>

        <div :class="{'hide': !editProfile}" slot="profile">
            <label for="">Họ và tên:</label>
            <input type="text">
            <label for="">Giới tính:</label>
            <input type="text">
            <label for="">Mail:</label>
            <input type="email">
            <label for="">Ngày sinh:</label>
            <input type="text">
            <label for="">Điện thoại:</label>
            <input type="text">
            <label for="">Địa chỉ:</label>
            <input type="text">
            <button>OK</button>
        </div>

        <div :class="{'hide': !editEdu}" slot="edu">
            <label for="">Trường:</label>
            <input type="text">
            <label for="">Chuyên ngành:</label>
            <input type="text">
            <label for="">Bằng cấp:</label>
            <input type="text">
            <label for="">GPA:</label>
            <input type="text">
            <button>OK</button>
        </div>

        <div :class="{'hide': !editSkill}" slot="skill">
            <label for="">Front-end:</label>
            <input type="text">
            <label for="">Back-end:</label>
            <input type="text">
            <label for="">Database:</label>
            <input type="text">
            <label for="">Framework:</label>
            <input type="text">
            <button>OK</button>
        </div>

        <div :class="{'hide': !editHob}" slot="hob">
            <input type="text">
            <button>OK</button>
        </div>

        <div :class="{'hide': !editRef}" slot="ref">
            <label for="">Họ và tên:</label>
            <input type="text">
            <label for="">Email:</label>
            <input type="email">
            <label for="">Công ty:</label>
            <input type="text">
            <button>OK</button>
        </div>
  </form-edit>
</template>

<script>
import Edit from './form-edit.vue'

export default {
    components: {
        'form-edit': Edit
    },
    data() {
        return {
            
        }
    }
}
</script>

<style>

</style>