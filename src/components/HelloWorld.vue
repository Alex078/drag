<template>
    <div class="row">
        <div class="col-3">
            <h3>Draggable 1</h3>
            <draggable
                    class="list-group"
                    :list="list1"
                    v-bind="dragOptions"
                    group="people"
                    @change="log">
                <transition-group class="list-group-item">
                    <li
                            class="list-group-item"
                            v-for="(element, index) in list1"
                            :key="element.id"
                    >
                        {{ element.name }} {{ element.id }}
                    </li>
                </transition-group>
            </draggable>
        </div>

        <div class="col-3">
            <h3>Draggable 2</h3>
            <draggable
                    class="list-group"
                    :list="list2"
                    v-bind="dragOptions"
                    group="people"
                    @change="log">
                <transition-group class="list-group-item">
                    <li
                            class="list-group-item"
                            v-for="(element, index) in list2"
                            :key="element.id"
                    >
                        {{ element.name }} {{ element.id }}
                    </li>
                </transition-group>
            </draggable>
        </div>

        <div class="col-3">
            <h3>Draggable 3</h3>
            <draggable
                    class="list-group"
                    :list="list3"
                    v-bind="dragOptions"
                    group="people"
                    @change="log">
                <transition-group class="list-group-item">
                    <li
                            class="list-group-item"
                            v-for="(element, index) in list3"
                            :key="element.id"
                    >
                        {{ element.name }} {{ element.id }}
                    </li>
                </transition-group>
            </draggable>
        </div>
    </div>
</template>
<script>
    import draggable from "vuedraggable";
    export default {
        name: "two-lists",
        order: 1,
        components: {
            draggable
        },
        data() {
            return {
                list1: [
                    { name: "John", id: 1 },
                    { name: "Joao", id: 2 },
                    { name: "Jean", id: 3 },
                    { name: "Gerard", id: 4 }
                ],
                list2: [
                    { name: "Juan", id: 5 },
                    { name: "Edgard", id: 6 },
                    { name: "Johnson", id: 7 }
                ],
                list3: [
                    { name: "Juanf", id: 8 },
                    { name: "Edgarde", id: 9 },
                    { name: "Johnsonrrt", id: 10 }
                ]
            };
        },
        methods: {
            add: function() {
                this.list.push({ name: "Juan" });
            },
            replace: function() {
                this.list = [{ name: "Edgard" }];
            },
            clone: function(el) {
                return {
                    name: el.name + " cloned"
                };
            },
            log: function(evt) {
                window.console.log(evt);
            }
        },
        computed: {
            dragOptions() {
                return {
                    animation: 200
                };
            }
        }
    };
</script>
