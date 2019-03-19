<template>
    <div class="users-information">
        <br><br>
        <div class="row justify-content-md-center">
            <div class="col-md-10">
                <div class="card">
                    <div class="card-header">
                        <span><i class="fas fa-users"></i>
                        &nbsp;&nbsp;
                        All Users</span>

                        <div class="card-tools">
                            <button type="button" class="btn btn-sm btn-primary" data-toggle="modal" data-target="#addUserModal">
                                <i class="fas fa-plus"></i>&nbsp;&nbsp;Add user
                            </button>
                        </div>
                    </div>
                    <div class="card-body p-0">
                        <table class="table">
                            <tbody>
                                <tr>
                                    <th style="width: 10px">#</th>
                                    <th>Task</th>
                                    <th>Progress</th>
                                    <th style="width: 40px">Label</th>
                                </tr>
                                <tr>
                                    <td>1.</td>
                                    <td>Update software</td>
                                    <td>
                                        <div class="progress progress-xs">
                                            <div class="progress-bar progress-bar-danger" style="width: 55%"></div>
                                        </div>
                                    </td>
                                    <td><span class="badge bg-danger">55%</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <!-- /.card-body -->
                </div>
            </div>
        </div>


        <!--Add user modal-->
        <div class="modal fade" id="addUserModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered" role="document">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title" id="exampleModalLongTitle">Add user</h5>
                        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                        </button>
                    </div>
                    <form>
                    <div class="modal-body">
                        <div class="form-group">
                            <label for="name">Full name</label>
                            <input v-model="form.name" type="text" name="name"
                                   class="form-control" :class="{ 'is-invalid': form.errors.has('name') }" id="name" placeholder="Enter name">
                            <has-error :form="form" field="name"></has-error>
                        </div>
                        <div class="form-group">
                            <label for="email">Email address</label>
                            <input v-model="form.email" type="email" name="email"
                                   class="form-control" :class="{ 'is-invalid': form.errors.has('email') }" id="email" placeholder="Enter email">
                            <has-error :form="form" field="email"></has-error>
                        </div>
                        <div class="form-group">
                            <label for="password">Password</label>
                            <input v-model="form.password" type="password" name="password"
                                   class="form-control" :class="{ 'is-invalid': form.errors.has('password') }" id="password" placeholder="Enter password">
                            <has-error :form="form" field="password"></has-error>
                        </div>
                        <div class="form-group">
                            <label for="password_confirmation">Confirm Password</label>
                            <input v-model="form.password_confirmation" type="password" name="password_confirmation"
                                   class="form-control" :class="{ 'is-invalid': form.errors.has('password_confirmation') }" id="password_confirmation" placeholder="Confirm password">
                            <has-error :form="form" field="password_confirmation"></has-error>
                        </div>
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-sm btn-secondary" data-dismiss="modal">Close</button>
                        <button type="button" class="btn btn-sm btn-primary">Add user</button>
                    </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                form: new Form({
                    name: '',
                    email: '',
                    password: '',
                    password_confirmation: ''
                })
            }
        },

        mounted() {
            console.log('Component mounted.')
        }
    }
</script>



