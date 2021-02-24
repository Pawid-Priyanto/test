<template>
    <div class="container">
				<RadioButton
					id="radioButton"
					v-model="fields.radio_button"
					:options="radio_button_options"
					label="Radio Button"
				>
					<template #textField>
						<br>
						<label for="textField"></label>
						<input
							type="text"
							id="textField"
							name="textField"
							v-model="fields.text_field"
							placeholder="Hey!"
						/>
					</template>

					<template #dateField>
						<br>
						<label for="dateField"></label>
						<input
							type="date"
							id="dateField"
							name="dateField"
							v-model="fields.date_field"
						/>
					</template>

					<template #form>
                      
						<form >
							<label>Name :</label>
							<input type="text" name="name" placeholder="Input Name" />
                            <button @click="add" type="submit">add</button>
						</form>
                       
					</template>
				</RadioButton>
			</div>
</template>

<script>
import RadioButton from './Radio'
export default {
    components: {
        RadioButton
    },
    data(){
        return{
				fields: {
					radio_button: null,
					text_field: "",
					date_field: "",
                    name: '',
				},
				radio_button_options: [
					{
						value: "textField",
						text: "Radio Button A",
					},
					{
						value: "dateField",
						text: "Radio Button B",
					},
					{
						value: "form",
						text: "Radio Button C"
					}
				]
			}
		},
    methods: {
        add: function(value) {
            console.log('add', value);
        },
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
