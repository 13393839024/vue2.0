<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>v-for</title>
    <script src="../assets/js/vue.js"></script>
</head>

<body>
    <h1>实例练习</h1>
    <hr>
    <div id="app">
        <ul>
            <li v-for="(item,aaa) in Toitems">
                {{aaa+1}}:{{item}}
            </li>
        </ul>
        <hr>
        <ul>
            <li v-for="(objects,index) in Toobject">
                {{index+1}}:{{objects.name}}---{{objects.age}}
            </li>
        </ul>
    </div>
    <script>
        var app = new Vue({
            el: "#app",
            data: {
                items: [12, 35, 9, 484, 468, 465, 42, 414, 5],
                object: [{
                    name: "sing",
                    age: 32
                }, {
                    name: "song",
                    age: 23
                }, {
                    name: "tirge",
                    age: 16
                }, {
                    name: "panda",
                    age: 6
                }]
            },
            computed: {
                Toitems: function() {
                    return this.items.sort(Sortnumber);
                },
                Toobject: function() {
                    return Sortobj(this.object, "age")
                }
            }
        });

        function Sortnumber(a, b) {
            return a - b;
        };

        function Sortobj(array, key) {
            return array.sort(function(a, b) {
                var x = a[key];
                var y = b[key];
                return ((x < y) ? -1 : ((x > y) ? 1 : 0))
            })
        }
    </script>
</body>

</html># vue2.0
