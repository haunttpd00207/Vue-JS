<template>
  <div>
    <h2 class="h1-responsive font-weight-bold text-center my-4">Contact us</h2>
    <form id="contact-form" name="contact-form" action="mail.php" method="POST">
    <slot name="top"></slot>
      <div class="row">
        <div class="col-md-6">
          <div class="md-form mb-0">
            <input type="text" id="name" name="name" class="form-control" placeholder="Typing your name" />
            <label for="name" class>Your name</label>
          </div>
        </div>
        <div class="col-md-6">
          <div class="md-form mb-0">
            <input type="text" id="email" name="email" class="form-control" placeholder="Typing your email address" />
            <label for="email" class>Your email</label>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <div class="md-form mb-0">
            <input type="text" id="subject" name="subject" class="form-control" placeholder="Typing your subject" />
            <label for="subject" class>Subject</label>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <div class="md-form">
            <textarea
              type="text"
              id="message"
              name="message"
              rows="2"
              class="form-control md-textarea"
              placeholder="Typing your message to us"
            ></textarea>
            <label for="message">Your message</label>
          </div>
        </div>
      </div>
    </form>
    <slot name="bottom">This is first comment</slot>
    <button class="btn btn-primary">Send</button>
  </div>
</template>

<script>
    import { eventBus } from "./main";
    
    export default {

    };
</script>