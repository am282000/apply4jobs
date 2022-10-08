<template>
  <div class="home">
    <h1>Veersa Technologies</h1>
    <p>Apply for your dream job !!</p>
    <button @click="togglePopUp">Add new Job</button>
    <div class="jobs">
      <!-- Jobs to go here -->
    </div>
    <div class="add-job-popup" v-if="popupOpen">
      <div class="popup-content">
        <span class="header">
          <h2>Apply Job</h2>
          <h3 class="close-btn" @click="togglePopUp">❌</h3>
        </span>
        <form @submit.prevent="">
          <div class="group">
            <label>Role 🌟</label>
            <input type="text" />
          </div>
          <div class="group">
            <label>Introduction 💭</label>
            <textarea></textarea>
          </div>
          <div class="group">
            <label>Skills 💯</label>
            <div class="skills">
              <input type="text" />
            </div>
            <button type="button" @click="addSkills">Add Skills 🦩</button>
          </div>
          <div class="group">
            <label>Why should we hire you ? 🤔</label>
            <div class="hire">
              <textarea></textarea>
            </div>
            <button class="achievements" type="button">
              Achievements(if any) 🏆
            </button>
          </div>

          <button type="submit">Submit</button>
          <button type="button" @click="togglePopUp">Close</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      form: {
        jobs: "",
        role: "",
        introduction: "",
        skillRows: [],
        hire: "",
        achievements: [],
      },
      popupOpen: false,
    };
  },
  methods: {
    togglePopUp() {
      this.popupOpen = !this.popupOpen;
    },
    addSkills() {
      // this.form.skillRows++;
      // console.log(this.form.skillRows);
      // debugger;
    },
  },
};
</script>

<style>
.home {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.header {
  display: flex;
  justify-content: space-between;
}
h2 {
  cursor: default;
}
.home p {
  font-size: 1rem;
  margin-bottom: 2rem;
}
.jobs {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}
.jobs .card {
  padding: 1rem;
  border-radius: 5px;
  margin: 1rem;
  background-color: #081c33;
}
.close-btn {
  border-radius: 45%;
  color: crimson;
  cursor: pointer;
}
.jobs .card h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
}
.jobs .card p {
  font-size: 1.125rem;
  line-height: 1.4;
  margin-bottom: 1rem;
}
.add-job-popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}
.add-job-popup .popup-content {
  background-color: #081c33;
  padding: 2rem;
  border-radius: 1rem;
  width: 100%;
  max-width: 768px;
}
.popup-content h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
}
.popup-content .group {
  margin-bottom: 1rem;
}
.popup-content .group label {
  display: block;
  margin-bottom: 0.5rem;
}
.popup-content .group .achievements {
  background-color: yellow;
}
.popup-content .group input,
.popup-content .group textarea {
  display: block;
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 1rem;
}
.popup-content .group textarea {
  height: 100px;
  resize: none;
}
.popup-content button[type="submit"] {
  margin-right: 1rem;
}
</style>
