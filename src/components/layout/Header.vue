<template>
    <div class="header">
        
        <div v-bind:class="{'nav-active':nav_active, 'nav-inactive':!nav_active, 'nav-container':true}">
            <div class="date-container">
            <h2>{{date.day}}</h2>
            <h4>{{date.calendar}}</h4>
        </div>
           <div class="routes-btn">
                <router-link to="/">Home</router-link>
                <router-link to="/admin">Admin</router-link>
           </div>
           <div class="menu" @click="toggleNav()">
                <ul>
                    <li class="first-line"></li>
                    <li class="second-line"></li>
                    <li class="third-line"></li>
                </ul>
            </div>
        </div>
        
    </div>
</template>

<script>
import moment from 'moment';
export default {
    name:'Header',
    data(){
        return{
            date:{},
            nav_active:false
        }
    },
    methods:{
        setDate(){
   
           this.date ={
               day:  moment().format('dddd'),
               calendar: moment().format('LL')
           } 
        },

        toggleNav(){
            this.nav_active = !this.nav_active;
        }
    },
    created(){
        this.setDate()
    }
}
</script>

<style lang="scss">
        .header{
            background:rgb(241, 241, 241);
            width: 100%;
            height: 150px;

            display: flex;
            align-items: center;
            justify-content: space-between;

            padding: 0 30px 0 30px;

            border-top: 5px solid #FA749C;
            border-bottom: 1.5px solid #e4e4e4;
            
        }
        .date-container{
            font-family: 'Roboto', sans-serif;

            h2{
                color:rgb(153, 145, 147);
            }
            h4{
                color: rgba(187, 179, 181, .8);
                font-style: italic;

            }
        }
        .menu{
                cursor: pointer;
                ul{
                    list-style: none;
                   li{
                     background:black;
                     width: 17px; 
                     border: 1px solid black;                    
                     border-radius: 25px;
                     margin: 4px 0px;  
                 }   
                }
            }
        .nav-active{
            .routes-btn{
                width: 100%;
                display: flex;
                justify-content: flex-start;
                *{
                    text-decoration: none;
                    font-family: 'Roboto', sans-serif;
                    font-weight: 300;
                    font-size: 20px;
                    margin: 0 15px;
                    color: rgb(153, 145, 147);

                    &:first-child{
                        margin-left: 0;
                    }
                    &:hover{
                        color: #FA749C;
                    }
                }
            }
             .date-container{
                display: none;
            }
            
            
            
        }
        .nav-inactive{
            .routes-btn{
                display: none;
            }
           
            
        }
        .nav-container{
            display: flex;
            flex-direction: row;
            align-items: center;
            justify-content: space-between;
            
            width: 100%;
        }
    
</style>
