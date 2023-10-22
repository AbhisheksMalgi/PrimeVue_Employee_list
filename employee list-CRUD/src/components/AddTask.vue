<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label>FirstName</label>
            <input class="p-inputtext p-component" type="text" v-model="firstName" name="firstname"
                placeholder="FirstName" />
        </div>
        <div class="form-control">
            <label>LastName</label>
            <input class="p-inputtext p-component" type="text" v-model="lastName" name="lastname" placeholder="LastName" />
        </div>
        <div class="form-control">
            <label>Department</label>
            <input class="p-inputtext p-component" type="text" v-model="department" name="department"
                placeholder="Department" />
        </div>
        <div class="form-control">
            <label>Info</label>
            <input class="p-inputtext p-component" type="text" v-model="info" name="info" placeholder="Info" />
        </div>
        <div class="form-control form-control-check">
            <label>Active</label>
            <input type="checkbox" v-model="active" name="active" />
        </div>
        <input type="submit" value="Save" class=" btn btn-block p-button" />
    </form>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            firstName: '',
            lastName: '',
            department: '',
            info: '',
            active: false
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()

            if (!this.firstName) {
                alert('Please add a task')
                return
            }

            const newTask = {
                firstName: this.firstName,
                lastName: this.lastName,
                department: this.department,
                info: this.info,
                active: this.active,
            }

            this.$emit('add-task', newTask)

            this.firstName = ''
            this.lastName = ''
            this.department = ''
            this.info = ''
            this.active = false
        },
    },
}
</script>

<style scoped>
.add-form {
    margin-bottom: 40px;
}

.form-control {
    margin: 20px 0;
}

.form-control label {
    display: block;
}

.form-control input {
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}

.form-control-check {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.form-control-check label {
    flex: 1;
}

.form-control-check input {
    flex: 2;
    height: 20px;
}

.p-component * {
    box-sizing: border-box;
}

.p-inputtext {
    font-size: 1rem;
    color: #033d78;
    background: #fff;
    padding: 0.75rem 0.75rem;
    border: 1px solid #8b8b8b;
    transition: background-color .2s, color .2s, border-color .2s, box-shadow .2s;
    appearance: none;
    border-radius: 6px;
}
</style>