<template>
  <div class="about">
    <div class="card">
      <div class="card-header">
        <b-icon icon="person-fill"></b-icon> Personal Infomation
      </div>
      <div class="card-body">
        <div class="row">
          <div class="col" style="text-align: center !important">
            <img
              src="https://files.fm/thumb_show.php?i=ecz7mu5hk"
              class="rounded mx-auto d-block"
            />
            <h5 class="card-title">
              {{ personalInfo.firstName }} - {{ personalInfo.lastName }}
            </h5>
          </div>
          <div class="col">
            <div class="row">
              <div class="col-sm-3">
                <strong>Date of birth</strong>
              </div>
              <div class="col-sm-3">
                <i class="card-text">
                  {{ personalInfo.dateOfBirth }}
                </i>
              </div>
            </div>

            <div class="row">
              <div class="col-sm-3">
                <strong>Country</strong>
              </div>
              <div class="col-sm-3">
                <i class="card-text">
                  {{ personalInfo.country }}
                </i>
              </div>
            </div>

            <div class="row">
              <div class="col-sm-3">
                <strong>Current address</strong>
              </div>
              <div class="col-sm-7">
                <i class="card-text">
                  {{ personalInfo.currentAddress }}
                </i>
              </div>
            </div>

            <div class="row">
              <div class="col-sm-3">
                <strong>Email</strong>
              </div>
              <div class="col-sm-7">
                <i class="card-text">
                  {{ personalInfo.email }}
                </i>
              </div>
            </div>

            <div class="row">
              <div class="col-sm-3">
                <strong>Phone number</strong>
              </div>
              <div class="col-sm-3">
                <i class="card-text">
                  {{ personalInfo.phoneNumber }}
                </i>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      personalInfo: {
        firstName: "Dung",
        lastName: "Ho",
        dateOfBirth: "November, 1999",
        country: "Binh Dinh, Viet Nam",
        currentAddress:
          "Number 35/18A, number 11 street, ward Linh Chieu, district Thu Duc, Ho Chi Minh city, Viet Nam",
        email: "..........@gmail.com",
        phoneNumber: "+84 3694 59077",
      },
    };
  },
};
</script>
<style scoped>
.rounded {
  height: 200px;
  width: 200px;
  border-radius: 50% !important;
  box-shadow: 0.375rem 0.375rem 0 0 rgba(15, 28, 63, 0.125);
}

.row {
  text-align: left !important;
}

strong{
  color: lightpink;
}
</style>
