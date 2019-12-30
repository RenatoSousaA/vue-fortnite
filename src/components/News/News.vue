<template>
    <div class="row justify-content-center mb-4">
        <div class="col-md-9">
            <div class="card">
                <div class="card-body">
                    <h5>Adicione aqui seus amigos</h5>
                    <table class="table table-striped table-dark mt-4">
                        <thead>
                            <tr>
                                <th scope="col">Nick name</th>
                                <th scope="col">Nome completo</th>
                                <th scope="col">Data de Criacao</th>
                                <th scope="col">(-)</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-bind:class="[friends.length > 1 ? '' : 'disabled']">
                                <td></td>
                                <td>
                                    Filtrar amigos =>
                                </td>
                                <td>
                                    <input type="text" v-model="filter" @keyup="getFriends" placeholder="Informe parte do nome" />
                                </td>
                                <td></td>
                            </tr>
                            <tr v-for="friend in auxFriends" :key="friend.id">
                                <td>
                                    <input type="text" v-model="friend.nickName" placeholder="Digite o Nick name" />
                                </td>
                                <td>
                                    <input type="text" v-model="friend.fullName" placeholder="Digite o nome completo" />
                                </td>
                                <td>
                                    {{ friend.createDate.toLocaleString("pt-BR") }}
                                </td>
                                <td><button class="btn-del-row" @click="delRow(friend.id)">(-) Remover</button></td>
                            </tr>
                            <tr>
                                <td></td>
                                <td></td>
                                <td>
                                    <button class="btn-add-row" @click="addRow">(+) Nova linha</button>
                                </td>
                                <td></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    import { uuid } from 'vue-uuid';

    export default {
        methods: {
            addRow() {
                this.friends.push({
                    id: uuid.v1(),
                    nickName: "",
                    fullName: "",
                    createDate: new Date()
                });
                this.getFriends();
            },
            delRow(id) {
                if (!confirm('Confirma exclusao?')) { return }
                this.friends = this.friends.filter((friend) => {
                    if (friend.id != id) {
                        return friend;
                    }
                });
                this.getFriends();
            },
            getFriends() {
                if (this.filter.length > 0) {
                    this.auxFriends = this.friends.filter((friend) => {
                        if (friend.fullName.includes(this.filter)) {
                            return friend;
                        }
                    });
                } else {
                    this.auxFriends = this.friends;
                }
            }
        },
        data() {
            return {
                auxFriends: [],
                friends: [],
                filter: ""
            }
        },
    };
</script>

<style scoped>

    h5,
    label {
        color: rgb(82, 82, 82);
    }

    .disabled {
        display: none
    }

</style>
