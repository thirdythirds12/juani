<template>
  <form class="contact-form" @submit.prevent="sendEmail">
    <label>Name</label>
    <input type="text" name="user_name" />
    <label>Email</label>
    <input type="email" name="user_email" />
    <label>Message</label>
    <textarea name="message"></textarea>
    <input type="submit" value="Send" class="btn btn-primary" data-toggle="modal" href="#ignismyModal" />
  </form>
  <a 
    >open Popup</a
  >
  <div class="modal fade" id="ignismyModal" role="dialog">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <button
            type="button"
            class="close"
            data-dismiss="modal"
            aria-label=""
          >
          <a href="/">
            <span>×</span>
            </a>
          </button>
        </div>

        <div class="modal-body">
          <div class="thank-you-pop">
            <img
              src="http://goactionstations.co.uk/wp-content/uploads/2017/03/Green-Round-Tick.png"
              alt=""
            />
            <h1>Thank You!</h1>
            <p>Your submission is received and we will contact you soon</p>
            <h3 class="cupon-pop">Your Id: <span>12345</span></h3>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  methods: {
    sendEmail: (e) => {
      emailjs
        .sendForm(
          "service_s6k86dp",
          "template_1enawjm",
          e.target,
          "user_RP2pvq17FV0BS0kcbFIEQ"
        )
        .then(
          (result) => {
            console.log("SUCCESS!", result.status, result.text);
          },
          (error) => {
            console.log("FAILED...", error);
          }
        );
    },
  },
};
</script>
<style lang="css">
/*--thank you pop starts here--*/
.thank-you-pop {
  width: 100%;
  padding: 20px;
  text-align: center;
}
.thank-you-pop img {
  width: 76px;
  height: auto;
  margin: 0 auto;
  display: block;
  margin-bottom: 25px;
}

.thank-you-pop h1 {
  font-size: 42px;
  margin-bottom: 25px;
  color: #5c5c5c;
}
.thank-you-pop p {
  font-size: 20px;
  margin-bottom: 27px;
  color: #5c5c5c;
}
.thank-you-pop h3.cupon-pop {
  font-size: 25px;
  margin-bottom: 40px;
  color: #222;
  display: inline-block;
  text-align: center;
  padding: 10px 20px;
  border: 2px dashed #222;
  clear: both;
  font-weight: normal;
}
.thank-you-pop h3.cupon-pop span {
  color: #03a9f4;
}
.thank-you-pop a {
  display: inline-block;
  margin: 0 auto;
  padding: 9px 20px;
  color: #fff;
  text-transform: uppercase;
  font-size: 14px;
  background-color: #8bc34a;
  border-radius: 17px;
}
.thank-you-pop a i {
  margin-right: 5px;
  color: #fff;
}
#ignismyModal .modal-header {
  border: 0px;
}
</style>