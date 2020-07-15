<template>
    <div id="app">
        <v-app id="inspire">
            <v-app id="inspire">
            <v-main>
                <v-container
                class="fill-height"
                fluid
                >
                <v-row
                    align="center"
                    justify="center"
                >
                    <v-col
                    cols="12"
                    sm="8"
                    md="4"
                    >
                    <v-card class="elevation-12">
                        <v-toolbar
                        color="primary"
                        dark
                        flat
                        >
                        <v-toolbar-title>SuperAdmin Login</v-toolbar-title>
                        <v-spacer></v-spacer>
                        </v-toolbar>
                        <v-card-text>
                        <v-form
                            ref="form"
                            v-model="valid">
                            <v-text-field
                            label="Username or email"
                            name="login"
                            v-model="loginDetail.userName"
                            :rules="userRules"
                            prepend-icon="mdi-account"
                            type="text"
                            ></v-text-field>
                            
                            <v-text-field
                            id="password"
                            label="Password"
                            name="password"
                            v-model="loginDetail.password"
                            :rules="passwordRules"
                            prepend-icon="mdi-lock"
                            :append-icon="value ? 'mdi-eye' : 'mdi-eye-off'"
                            @click:append="() => (value = !value)"
                            :type="value ? 'password' : 'text'"
                            ></v-text-field>
                        </v-form>
                        </v-card-text>
                        <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn color="primary" @click="loginToSuperAdmin">Login</v-btn>
                        </v-card-actions>
                    </v-card>
                    </v-col>
                </v-row>
                </v-container>
            </v-main>
            </v-app>
        </v-app>
    </div>
</template>

<script>
export default {
    data :() =>({
        valid: true,
        loginDetail: {
            userName: '',
            password: ''
        },
        value: String,
        userRules: [
            a => !!a || 'Username is required'
        ],
        passwordRules:[
            a => !!a || 'Password is required'
        ]
    }),
    methods: {
        validateForm(){
            this.$refs.form.validate()
        },
        loginToSuperAdmin(){
            this.validateForm();
            if(!this.valid) return;
            alert();
        }
    }
}
</script>