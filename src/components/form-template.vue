<template>
  <div class='form-wrap'>
      <!-- HEADER -->
      <div class="header">
          <div class="header__inf" style="flex:2;">
              <h1>{{name}}</h1>
              <p>{{job}}</p>
              <div style="border: 3px solid white; border-width: 5px; width: 70px; margin: 10px 0px;"></div>
              <div class="header__objective">
                <h4>MỤC TIÊU NGHỀ NGHIỆP</h4>
                <ul>
                    <li>- {{obj[0]}}</li>
                    <li>- {{obj[1]}}</li>
                </ul>
              </div>
          </div>
          <div class="header__ava" style="flex:1">
              <img src="../assets/avatar.jpg" alt="" width="100%">
          </div>
      </div>

    <!-- MAIN CONTENT -->
      <div class="content">
          <!-- Left side -->
            <div class="content__left">
                <div class="content__detail">
                    <h2>
                        <i class="fal fa-angle-double-right fa-2x"></i>
                        <span>KINH NGHIỆM LÀM VIỆC</span>
                    </h2>

                    <div class="detail__exp left-side__detail">
                        <div class="detail__time">
                            <div class="detail__time--1">
                                <span>{{exp.thoigian}}</span>
                            </div>
                        </div>

                        <div class="detail__text">
                            <h4>{{exp.congty}}</h4>
                            <p>{{exp.vitri}}</p>
                            <h5 style="font-size: 105%;">Mô tả</h5>
                            <ul>
                                <li>- {{exp.mota[0]}}</li>
                                <li>- {{exp.mota[1]}}</li>
                                <li>- {{exp.mota[2]}}</li>
                                <li>- {{exp.mota[3]}}</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="content__detail">
                    <h2>
                        <i class="fal fa-angle-double-right fa-2x"></i>
                        <span>HỌC VẤN</span>
                    </h2>

                    <div class="detail__edu left-side__detail">
                        <div class="detail__time">
                            <div class="detail__time--1">
                                <span>07/2017 - present</span>
                            </div>
                        </div>
                        <div class="detail__text">
                            <h4>ĐẠI HỌC BÁCH KHOA HÀ NỘI</h4>
                            <p> <b>Chuyên ngành:</b> Kỹ thuật phần mềm </p>
                            <p> <b>Bằng cấp: </b> Kỹ sư </p>
                            <p> <b>GPA: </b> 2.5 </p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Right side -->
            <div class="content__right">
                <div class="content__detail">
                    <h2>
                        <i class="fal fa-angle-double-right fa-2x"></i>
                        <span>THÔNG TIN CÁ NHÂN</span>
                    </h2>
                    
                    <div class="detail__inf">
                        <p> <b>Họ và tên:</b> {{inf.hoten}} </p>
                        <p> <b>Giới tính:</b> {{inf.gioitinh}} </p>
                        <p> <b>Mail:</b> {{inf.mail}} </p>
                        <p> <b>Ngày sinh:</b> {{inf.ngaysinh}} </p>
                        <p> <b>Điện thoại:</b> {{inf.dienthoai}} </p>
                        <p> <b>Địa chỉ:</b> {{inf.diachi}} </p>
                    </div>
                </div>

                <div class="content__detail">
                    <h2>
                        <i class="fal fa-angle-double-right fa-2x"></i>
                        <span>KỸ NĂNG</span>
                    </h2>

                    <div class="detail_skill">
                        <p> <b>Front-end:</b> HTML,CSS,JS </p>
                        <p> <b>Back-end:</b> Python-Flask, NodeJS </p>
                        <p> <b>Database:</b> Firebase, MongoDB </p>
                        <p> <b>Framework:</b> VueJS, Bootstrap </p>
                    </div>
                </div>

                <div class="content__detail">
                    <h2>
                        <i class="fal fa-angle-double-right fa-2x"></i>
                        <span>SỞ THÍCH</span>
                    </h2>

                    <div class="detail__hob">
                        <p>{{hobby}}</p>
                    </div>
                </div>
            </div>
      </div>

      <!-- FOOTER -->
      <div class="footer">
          <div class="footer__ref">
            <h2>
                <i class="fal fa-angle-double-right fa-2x"></i>
                <span>REFERENCE</span>
            </h2>

            <div class="detail__ref">
                <p> <b>Họ và tên:</b> Đào Tuấn Anh </p>
                <p> <b>Email:</b> anhdt@mindx.edu.vn </p>
                <p> <b>Công ty:</b> 0123456789 </p>
            </div>
          </div>

          <div class="footer__c">
              <p>Copyright by khanhnq298</p>
          </div>
      </div>

  </div>
</template>

<script>
import { bus } from "../main";

export default {
    data() {
        return {
            name: 'NGUYEN QUOC KHANH',
            job: 'Web developer',
            hobby: 'Too much to write',
            obj: ['Mong muốn học hỏi ở môi trường làm việc chuyên nghiệp, năng động',
            'Có cơ hội thăng tiến cao, thành công trong công việc.'],
            inf: {
                'hoten': 'Nguyen Quoc Khanh',
                'gioitinh': 'nam',
                'mail': 'khanhnq.298@gmail.com',
                'ngaysinh': '29/08/1999',
                'dienthoai': '0385384982',
                'diachi': 'Hoang Mai, Ha Noi'
            },
            exp: {
                'congty':'MindX', 
                'vitri':'Teacher',
                'mota': ['Hướng dẫn học sinh làm game bằng GameMaker Studio', 
                'Tổ chức lớp học', 
                'Tổ chức các event, workshop đưa công nghệ đến gần hơn với trẻ em', 
                'Hỗ trợ học viên làm các mini-project'],
                'thoigian': '01/2019 - present'
            }
        }
    },
    created() {
        bus.$on('editName', (data) => {
            this.name = data
        }),
        bus.$on('editJob', (data) => {
            this.job = data
        }),
        bus.$on('editHob', (data) => {
            this.hobby = data
        }),
        bus.$on('editObjective', (data) => {
            let temp = true
            for(let item of data) {
                if (item.length == 0) {
                    temp = false
                    break
                }
            }
            if (temp) {
                this.obj = data
            }
        }),
        bus.$on('editProfile', (data) => {
            let temp = true
            for(let item in data) {
                if (data[item].length == 0) {
                    temp = false
                    break
                }
            }
            if (temp) {
                this.inf = data
            }
        }),
        bus.$on('editExp', (data) => {
            let temp = true
            for(let item in data) {
                if (data[item].length == 0) {
                    temp = false
                    break
                }
            }
            if (temp) {
                this.exp = data
            }

        })
    }
}
</script>

<style >
ul {
    list-style-type: none;
    line-height: 20px;
    font-size: 15px;
    padding-inline-start: 0px;
    margin-block-start: 0px;
    margin-block-end: 0px;
}

.content h2 {
    color: var(--main-color);
    font-size: 18px;

    display: flex;
    align-items: center;
}

h2 i {
    margin-right: 5px;
}

.form-wrap {
    background-color: white;
    border: 1px solid black;
    width: 800px;
    height: 1055px;

    display: flex;
    flex-direction: column;
}

.header {
    flex: 1;
    display: flex;
    padding: 30px 40px;

    background-color: var(--main-color);
    color: white;
}

.header__inf {
    line-height: 40px;
}

.header__ava img {
    border: 1px solid black;
    border-radius: 50%;
    width: 85%;

    display: block;
    margin: auto;
    margin-top: 10px;
}

.content {
    flex: 3;
    display: flex;
    margin: 30px 0px;
}

.content__detail {
    margin-top: 20px;
}

.content__left {
    flex: 1.2;
    margin-left: 0px;
}

.content__left h2 {
    margin-left: 100px;
}

.left-side__detail {
    display: flex;
}

.left-side__detail .detail__text {
    flex: 3;
}

.left-side__detail .detail__time {
    flex: 1.2;
    border-right: 1px solid var(--main-color);
    width: 100%;
    margin: 0px;
}

.detail__time--1 {
    width: 100%;
    margin-left: 0px !important;
    border: 1px solid var(--main-color);
    border-right: 0px;
    text-align: center;
}

.detail__time--1 span {
    font-size: 10px;
    font-weight: bold;
}

.content__right {
    flex: 1;
    margin-left: 60px;
}

.content__detail {
    /* box-sizing: content-box; */
    /* height: fit-content; */
    /* width: 45%; */
    /* margin: 0 2.5%; */
}

.content__detail div {
    margin-left: 30px;
    line-height: 30px;
    font-size: 15px;
}

.footer {
    flex: 1;
    /* display: flex; */
    padding: 30px 40px;

    background-color: var(--main-color);
    color: white;
}

.footer .footer__ref {
    margin-left: 60px;

    line-height: 30px;
}

.footer h2 {
    color: white;
    font-size: 18px;

    display: flex;
    align-items: center;
}

.footer__c {
    text-align: center;
    font-style: italic;
    font-size: 12px;

    margin-top: 20px;
    margin-bottom: 0px;
}

.footer__c p {
    margin-block-end: 0px;
}

</style>