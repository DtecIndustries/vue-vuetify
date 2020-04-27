<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Signup</h1>

        <v-form>
          <!-- textfield -->
          <v-text-field label="Email" type="email"></v-text-field>

          <!-- autocompletes -->
          <v-autocomplete label="Which browser do you use?" :items="browsers"></v-autocomplete>

          <!-- file input -->
          <v-file-input label="Attach profile picture"></v-file-input>

          <!-- date picker -->
          <v-text-field label="birthday" v-model="birthday" readonly=""></v-text-field>
          <v-date-picker v-model="birthday"></v-date-picker>

          <!-- checkbox -->
          <v-checkbox label="Agree to terms & conditions"></v-checkbox>

          <!-- submit btn -->
          <v-btn type="submit" color="primary">Submit</v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      browsers: [
        'Chrome',
        'Firefox',
        'Safari',
        'Edge',
        'Brave'
      ],
      birthday: ''
    }
  }
}
</script>