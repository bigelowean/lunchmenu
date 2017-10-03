# lunchmenu





<!DOCTYPE html>

<html>
<head>
    <meta name="viewport" content="width=device-width" />
    <title>MenuPlanCalendarWebExport</title>

        <link rel="stylesheet" href="http://ajax.googleapis.com/ajax/libs/jquerymobile/1.4.5/jquery.mobile.min.css"/>
        <style>
        
        

            .ui-dialog-contain {
                margin-top: 30px;
                max-width: 1200px;
            }

            .ui-dialog-contain th {
                font-family: Verdana, Helvetica, "Arial Narrow";
                font-size: 12px;
            }

            .ui-dialog-contain td {
                font-family: Verdana, Helvetica, "Arial Narrow";
                font-size: 12px;
            }

            .ui-dialog-contain p {
                font-family: Verdana, Helvetica, "Arial Narrow";
                font-size: 12px;
            }

            .ui-dialog .ui-header,
            .ui-dialog .ui-content,
            .ui-dialog .ui-footer {
                max-width: 1200px;
                margin: auto auto 15px auto;
            }

            
        

            .NutrientTable tbody th {
                padding-top: 10px;
                padding-bottom: 10px;
                font-size: 14px;
            }

            @media (min-width: 1050px) {

                .NutrientTable,
                .AllergenTable {
                    table-layout: fixed;
                }

                .NutrientTableRecipeColumn {
                    width: 15%;
                }

                .NutrientTable tbody th,
                .AllergenTable tbody th {
                    font-size: 12px;
                    padding-top: 0;
                    padding-bottom: 0;
                }

                
                .NutrientTable td,
                .NutrientTable th,
                .NutrientTable tbody th,
                .NutrientTable tbody td,
                .NutrientTable thead td,
                .NutrientTable thead th,
                .AllergenTable td,
                .AllergenTable th,
                .AllergenTable tbody th,
                .AllergenTable tbody td,
                .AllergenTable thead td,
                .AllergenTable thead th {
                    display: table-cell;
                    margin: 0;
                }
                
                .NutrientTable td .ui-table-cell-label,
                .NutrientTable th .ui-table-cell-label,
                .AllergenTable td .ui-table-cell-label,
                .AllergenTable th .ui-table-cell-label {
                    display: none;
                }
            }


            

            .NutrientTable thead th,
            .NutrientTable tbody tr:last-child,
            .AllergenTable thead th,
            .AllergenTable tbody tr:last-child {
                border-bottom: 1px solid #d6d6d6; 
                border-bottom: 1px solid rgba(0, 0, 0, .1);
            }

            .NutrientTable tbody th,
            .NutrientTable tbody td,
            .AllergenTable tbody th,
            .AllergenTable tbody td {
                border-bottom: 1px solid #e6e6e6; 
                border-bottom: 1px solid rgba(0, 0, 0, .05);
            }

            .NutrientTable tbody tr:last-child th,
            .NutrientTable tbody tr:last-child td,
            .AllergenTable tbody tr:last-child th,
            .AllergenTable tbody tr:last-child td {
                border-bottom: 0;
            }

            .NutrientTable tbody tr:nth-child(odd) td,
            .NutrientTable tbody tr:nth-child(odd) th,
            .AllergenTable tbody tr:nth-child(odd) td,
            .AllergenTable tbody tr:nth-child(odd) th {
                background-color: #eeeeee; 
                background-color: rgba(0, 0, 0, .04);
            }
            

            .Meal-Nutrients {
                font-size: 12px;
                font-family: Verdana, Helvetica, "Arial Narrow";
            }

            .nutrientTableRecipeName {
                word-break: break-all;
            }

        
        
        
</style>
<style>
    body {
        font-family: Verdana, Helvetica, "Arial Narrow";
    }

    a:link {
        text-decoration: none;
    }

    a:visited {
        text-decoration: none;
    }

    #calendar {
        width: 100%;
        max-width: 1300px;
        margin-left: auto;
        margin-right: auto;
        border-spacing: 10px;
        page-break-inside: auto;
        border-collapse: separate;
        background-color: #F0F0F0;
    }

    #calendar a {
        color: #000000;
        text-decoration: none;
    }

    #calendar .weekdays {
        height: 20px;
        padding: 0;
        margin: 0;
    }

    #calendar .weekday {
        padding-top: 10px;
        padding-bottom: 10px;
        text-align: center;
        text-transform: uppercase;
        text-shadow: none;
        line-height: 10px;
        color: #ffffff;
        font-size: 16px;
        font-weight: bolder;
        text-transform: capitalize;
        border: 1px solid #000000;
        border-radius: 5px;
        background-color: #000000;
        color: #ffffff;
    }

    #calendar .days {
        padding: 0;
        margin: 0;
        width: 100%;
        page-break-inside: avoid;
        page-break-after: auto;
        min-height: 40px;
        page-break-inside: avoid;
    }

    #calendar .day {
        margin: 0;
        padding: 0;
        border-radius: 5px;
        border: 1px solid #ccc;
        vertical-align: top;
        text-align: center;
        background-color: #fff;
        padding-bottom: 5px;
        page-break-inside: avoid;
    }

    #calendar .day:hover {
        background: #d3d3d3;
    }

    #calendar .date {
        font-family: Arial;
        font-size:  6pt;
        font-weight: normal;
        text-align: right;
        background-color: #000000;
        border-bottom-left-radius: 5px;
        border-top-right-radius: 5px;
        margin-top: 0;
        margin-left: auto;
        text-shadow: none;

                width:50px;
    }

    #calendar .dateNumber {
        width: 100%;
        text-align: center;
        color: #ffffff;
    }

    #calendar .meal {
        font-family: Arial;
        font-size:  6pt;
        text-decoration: none;
        text-align: center;
        line-height: 1.3em;
            margin-top:5px;
    }

    #calendar .meal-desc {
        color: #666;
        text-decoration: none;
        text-align: center;
        word-break: break-all;
        text-shadow: none;
    }

    #calendar .nutrients-desc {
        color: #666;
        text-decoration: none;
        text-align: center;
        text-shadow: none;
    }

    #calendar .other-month {
        background: #f5f5f5;
        color: #666;
    }

    #printLink {
        text-align: right;
        max-width: 1300px;
        margin-right: auto;
        margin-left: auto;
    }

    /* ============================
             Mobile Responsiveness
           ============================*/

    @media (max-width: 859px) {
        #calendar .other-month {
            display: none;
        }
        #calendar .day {
            width: 100%;
            margin-bottom: 5px;
            border-collapse: collapse;
        }
        #calendar .date {
            background-color: transparent;
        }
        #calendar .dateNumber {
            color: #000;
            font-weight: bolder;
        }
    }

    @media (min-width: 860px), print {

        #calendar .other-month {
            display: table-cell;
        }

        /* Show the table header rows and set all cells to display: table-cell */
        #calendar td,
        #calendar th,
        #calendar tbody th,
        #calendar tbody td,
        #calendar thead td,
        #calendar thead th {
            display: table-cell;
        }

        /* Hide the labels in each cell */
        #calendar td .ui-table-cell-label,
        #calendar th .ui-table-cell-label {
            display: none;
        }

        #calendar .day {
                width: 20%;
        }
    }

    @media print {
        #printLink {
            display: none;
        }
        
        .Meal-Nutrients {
            display: none;
        }
        
        #one {
            min-height: 0 !important;
            height: auto;
        }
        
        #calendar .date {
            background-color: #000000;
        }
        #calendar .dateNumber {
            width: 100%;
            text-align: center;
            color: #ffffff;
        }
    }
    </style>
            <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
    <script src="http://ajax.googleapis.com/ajax/libs/jquerymobile/1.4.5/jquery.mobile.min.js"></script>
</head>
<body>
<div data-role="page" id="one">

    <div id="printLink">
        <a href="javascript:window.print()" class="ui-btn ui-btn-inline ui-icon-calendar ui-btn-icon-left ui-corner-all ui-shadow">
            Print this calendar
        </a>
    </div>

    
<style>
    #headerTable {
        width: 100%;
        max-width: 1300px;
        margin-left: auto;
        margin-right: auto;
        margin-bottom: 0;
        border-spacing: 0;
        border-collapse: collapse;
        border: 0;
        background-color: #fcfbfb;
        color: #000000;
        text-shadow: none;
        table-layout: fixed;
    }

    #headerTable td {
        font-family: Arial;
        font-size:  6pt;
        width: 33%;
    }

    #districtNameHeader {
        text-align: left;
        font-weight: bold;
    }

    #reportHeadingHeader {
        text-align: center;
        font-weight: bold;
    }

    #siteNameHeader {
        text-align: right;
        font-weight: bold;
    }

    #headingHeader {
        padding: 0;
        margin: 0;
        max-width: 100%;
    }

    #HeaderImage {
        display: block;
        margin-left: auto;
        margin-right: auto;
        max-width: 100%;
        width: auto;
        height: auto;
    }

</style>
<table id="headerTable">
    <tbody>
        <tr>
            <td id="districtNameHeader">
Johnsburg CUSD #12            </td>
            <td id="reportHeadingHeader">
Johnsburg School District                             </td>

            <td id="siteNameHeader">
            </td>
        </tr>
        <tr>
            <td colspan="3" id="headingHeader">


<p>&nbsp;</p><p style="text-align:center;"><i><b>Johnsburg Bloodhounds</b></i></p><p style="text-align:center;"><i><b>September 2017</b></i></p><p style="text-align:center;"><i><b></b></i><i>"Good Manners and Respect Are Always On Our Menu"</i></p><p style="text-align:center;"><i>Meal $3.00 Milk $.35</i></p><p style="text-align:center;"><i>Mrs. Wolk-FoodService Coordinator</i></p><p>&nbsp;</p>            </td>
        </tr>
    </tbody>
</table>



    <table id="calendar" data-role="table" data-mode="reflow">
        <thead>
        <tr class="weekdays">
            <th class="weekday">Monday</th>
            <th class="weekday">Tuesday</th>
            <th class="weekday">Wednesday</th>
            <th class="weekday">Thursday</th>
            <th class="weekday">Friday</th>
        </tr>
        </thead>
        
        <tbody>


                <tr class="days">
                <td class="day other-month">
            </td>
                <td class="day other-month">
            </td>
                <td class="day other-month">
            </td>
                <td class="day other-month">
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 1                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        OUR OWN GRILLED CHEESE                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        TOMATO SOUP                                                                            </span>
                            <br/>
                            <span>
                                        3 BEAN SALAD                                                                            </span>
                            <br/>
                            <span>
                                        APPLE, RED DELICIOUS                                                                            </span>
                            <br/>
                            <span>
                                        WELCH&#39;S FRUIT SNACK                                                                            </span>
                            <br/>
                            <span>
                                        MILK, 1% LOW FAT WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-01-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                </tr>
                <tr class="days">
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 4                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        ***HOLIDAY***                                                                            </span>
                            <br/>
                            <span>
                                        **NON-ATTENDANCE DAY***                                                                            </span>
                            <br/>
                            <span>
                            <span>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-04-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 5                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        PEPPERONI PIZZA WEDGE                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE GRAPE PBJ(wheat)                                                                            </span>
                            <br/>
                            <span>
                                        SPINACH/ROMAINE SALAD                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DRESSING, Light                                                                            </span>
                            <br/>
                            <span>
                                        APPLESAUCE (k)                                                                            </span>
                            <br/>
                            <span>
                                        CHOCOLATE CHIP COOKIE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-05-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 6                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        CHICKEN RINGS                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        CHERRY CRAISINS                                                                            </span>
                            <br/>
                            <span>
                                        TATER TOTS                                                                            </span>
                            <br/>
                            <span>
                                        WHOLE KERNEL CORN                                                                            </span>
                            <br/>
                            <span>
                                        ORANGE SHERBET CUP                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-06-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 7                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        PHILLY CHEESE STEAK on BUN                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        MASHED POTATO (jhs)                                                                            </span>
                            <br/>
                            <span>
                                        CARROTS, baby peeled                                                                            </span>
                            <br/>
                            <span>
                                        RANCH (jjhs)                                                                            </span>
                            <br/>
                            <span>
                                        FUJI APPLES                                                                            </span>
                            <br/>
                            <span>
                                        OREO COOKIES                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-07-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 8                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        SUPER SOFT PRETZEL (jcb)                                                                            </span>
                            <br/>
                            <span>
                                        CHEDDAR CHEESE SAUCE                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        BAKED BEANS                                                                            </span>
                            <br/>
                            <span>
                                        FRUITABLE TROPICAL TWIST                                                                            </span>
                            <br/>
                            <span>
                                        PEARS, SLICED in LIGHT SYRUP                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-08-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                </tr>
                <tr class="days">
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 11                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        FRENCH TOAST STICKS (wg)                                                                            </span>
                            <br/>
                            <span>
                                        SYRUP CUP                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE GRAPE PBJ(wheat)                                                                            </span>
                            <br/>
                            <span>
                                        PORK SAUSAGE PATTY                                                                            </span>
                            <br/>
                            <span>
                                        TRI-TATORS                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP                                                                            </span>
                            <br/>
                            <span>
                                        CHERRY TOMATOES                                                                            </span>
                            <br/>
                            <span>
                                        ORANGES                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-11-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 12                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        FRENCH BREAD GARLIC PIZZA                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        BROCCOLI FLORETS                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DRESSING, Light                                                                            </span>
                            <br/>
                            <span>
                                        APPLE, RED DELICIOUS                                                                            </span>
                            <br/>
                            <span>
                                        NUTTY BUDDY (wafer cookie)                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-12-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 13                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        POPCORN CHICKEN                                                                            </span>
                            <br/>
                            <span>
                                        BBQ SAUCE CUP                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        KRINKLE KUT FRIES                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP PACKET                                                                            </span>
                            <br/>
                            <span>
                                        CARROTS,BABY PEELED                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DRESSING, Light                                                                            </span>
                            <br/>
                            <span>
                                        PINEAPPLE/MANDARIN MIX                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-13-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 14                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        CHEESEBURGER on BUN                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP PACKET                                                                            </span>
                            <br/>
                            <span>
                                        MUSTARD                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE GRAPE PBJ(wheat)                                                                            </span>
                            <br/>
                            <span>
                                        KRINKLE KUT FRIES                                                                            </span>
                            <br/>
                            <span>
                                        BABY CARROTS (RAW)                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DRESSING, Light                                                                            </span>
                            <br/>
                            <span>
                                        APPLE SLICES                                                                            </span>
                            <br/>
                            <span>
                                        DILL PICKLE SPEAR                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-14-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 15                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        MINI CORN DOGS                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP PACKET                                                                            </span>
                            <br/>
                            <span>
                                        MUSTARD                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        BAKED BEANS                                                                            </span>
                            <br/>
                            <span>
                                        FRUITABLE TROPICAL TWIST                                                                            </span>
                            <br/>
                            <span>
                                        STRAWBERRY APPLESAUCE CUP                                                                            </span>
                            <br/>
                            <span>
                                        CHIPS AHOY 100 Calorie Pak                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-15-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                </tr>
                <tr class="days">
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 18                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        CHEDDAR CHEESE OMELETTE                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        ENGLISH MUFFIN                                                                            </span>
                            <br/>
                            <span>
                                        HASH BROWN PATTY                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP PACKET                                                                            </span>
                            <br/>
                            <span>
                                        CARROTEENIES                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DIPPING CUP 1 OZ                                                                            </span>
                            <br/>
                            <span>
                                        ORANGE WEDGES                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-18-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 19                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        BOSCO BREADSTICK                                                                            </span>
                            <br/>
                            <span>
                                        MARINARA SAUCE                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        CUCUMBER SLICES                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DRESSING, Light                                                                            </span>
                            <br/>
                            <span>
                                        STRAWBERRY APPLESAUCE CUP                                                                            </span>
                            <br/>
                            <span>
                                        CHOCOLATE CHIP COOKIE (wg)                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-19-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 20                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        CHICKEN DRUMSTICK                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        EMOJI FRIES                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP CUP                                                                            </span>
                            <br/>
                            <span>
                                        PEAPODS                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DIPPING CUP 1 OZ                                                                            </span>
                            <br/>
                            <span>
                                        APPLE SLICES                                                                            </span>
                            <br/>
                            <span>
                                        CHOCOLATE PUDDING                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-20-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 21                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        SPAGHETTI &amp; MEATBALLS (rw)                                                                            </span>
                            <br/>
                            <span>
                                        GARLIC TOAST                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        BROCCOLI FLORETS (fresh)                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DRESSING, Light                                                                            </span>
                            <br/>
                            <span>
                                        FRUIT COCKTAIL                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-21-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 22                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        HAM &amp; AMERICAN SANDWICH                                                                            </span>
                            <br/>
                            <span>
                                        MAYONNAISE PACKETS                                                                            </span>
                            <br/>
                            <span>
                                        MUSTARD (offered)                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        TINY TWIST PRETZELS                                                                            </span>
                            <br/>
                            <span>
                                        HUMMUS                                                                            </span>
                            <br/>
                            <span>
                                        CELERY STICKS                                                                            </span>
                            <br/>
                            <span>
                                        3 BEAN SALAD                                                                            </span>
                            <br/>
                            <span>
                                        MANDARIN ORANGE, whole segment                                                                            </span>
                            <br/>
                            <span>
                                        RICE KRISPIE TREAT                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-22-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                </tr>
                <tr class="days">
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 25                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        SAUSAGE, EGG AND CHEESE MUFFIN                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        V8 JUICE                                                                            </span>
                            <br/>
                            <span>
                                        STRAWBERRY YOGURT CUP(danimal)                                                                            </span>
                            <br/>
                            <span>
                                        CHERRY CRAISINS                                                                            </span>
                            <br/>
                            <span>
                                        WELCH&#39;S FRUIT SNACK                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-25-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 26                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        PERSONAL CHEESE PIZZA                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        SPINACH/ROMAINE SALAD                                                                            </span>
                            <br/>
                            <span>
                                        ITALIAN DRESSING(NEW)                                                                            </span>
                            <br/>
                            <span>
                                        APPLE, RED DELICIOUS                                                                            </span>
                            <br/>
                            <span>
                                        JELLO-STRAWBERRY                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-26-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 27                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        CHICKEN NUGGETS                                                                            </span>
                            <br/>
                            <span>
                                        BREAD &amp; BUTTER (rw)                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        KRINKLE KUT FRIES                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP PACKET                                                                            </span>
                            <br/>
                            <span>
                                        CARROTS,BABY PEELED                                                                            </span>
                            <br/>
                            <span>
                                        RANCH DRESSING, Light                                                                            </span>
                            <br/>
                            <span>
                                        APPLE JUICE-100%                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-27-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 28                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        BEEF HOT DOG on BUN                                                                            </span>
                            <br/>
                            <span>
                                        KETCHUP                                                                            </span>
                            <br/>
                            <span>
                                        MUSTARD                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        BAKED BEANS                                                                            </span>
                            <br/>
                            <span>
                                        FRUITABLE PLUS POWER PUNCH                                                                            </span>
                            <br/>
                            <span>
                                        PEACHES, sliced in light syrup                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-28-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                <td class="day">
                <div class="date">
                    <div class="dateNumber">
Sep 29                    </div>
                </div>
                <div class="meal">
                    <div class="meal-desc">

                            <span>
                                        MACARONI &amp; CHEESE                                                                            </span>
                            <br/>
                            <span>
                                        UNCRUSTABLE, GRAPE whole wheat                                                                            </span>
                            <br/>
                            <span>
                                        APPLE, RED DELICIOUS                                                                            </span>
                            <br/>
                            <span>
                                        GARLIC CHEDDAR BISCUIT                                                                            </span>
                            <br/>
                            <span>
                                        CUCUMBER SLICES                                                                            </span>
                            <br/>
                            <span>
                                        NUTTY BUDDY (wafer cookie)                                                                            </span>
                            <br/>
                            <span>
                                        MILK,1% Lowfat WHITE                                                                            </span>
                            <br/>
                            <span>
                                        MILK,Fat Free CHOCOLATE                                                                            </span>
                            <br/>
                    </div>
                </div>
                    <div class="Meal-Nutrients">

                        <a href="#Nutrients-09-29-2017" data-rel="dialog" data-transition="none">View Nutrients</a>

                    </div>
            </td>
                </tr>
        </tbody>
    </table>

    
<style>
    #footerTable {
        width: 100%;
        max-width: 1300px;
        margin-left: auto;
        margin-right: auto;
        margin-bottom: 0;
        border-spacing: 0;
        border-collapse: collapse;
        border: 0;
        background-color: #ffffff;
        color: #000000;
        text-shadow: none;
        table-layout: fixed;
         page-break-inside: avoid;
    }

    #FooterImage {
        display: block;
        max-width: 100%;
        width: auto;
        height: auto;
        margin-left: auto;
        margin-right: auto;
    }

    #footerTable td {
        font-family: Arial;
        font-size: 6pt;
        font-weight: bold;
    }

    #dateFooter {
        text-align: right;
    }

    #footerContent {
        padding: 0;
        margin: 0;
        max-width: 100%;
    }
</style>

<table id="footerTable">
    <tbody>
        <tr>
            <td id="footerContent">


<div style="text-align:center;">Your child must select the fruit and/or vegetable option each day*Milk is included with the purchase of a meal, additional milk is available at $.35*&nbsp;<b style="text-align:center;">THE DATA CONTAINED WITHIN THIS REPORT SHOULD NOT BE USED FOR AND DOES NOT PROVIDE MENU PLANNING FOR A CHILD WITH A MEDICAL CONDITION OR FOOD ALLERGY. &nbsp;INGREDIENTS AND MENU ITEMS ARE SUBJECT TO CHANGE WITHOUT NOTICE. &nbsp;PLEASE CONSULT A MEDICAL PROFESSIONAL FOR ASSISTANCE IN PLANNING OR TREATING MEDICAL CONDITIONS.</b></div><div style="text-align:center;"><b style="text-align:center;"><br /></b></div><div style="text-align:center;"></div>            </td>
        </tr>
    </tbody>
</table>

</div>

    
                    <div data-role="page" id="Nutrients-09-01-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Friday, September 1, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-01-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
OUR OWN GRILLED CHEESE                                    </td>

                                        <td>269</td>
                                                                            <td>4.24</td>

                                        <td>1012.28</td>
                                                                            <td>*1.70</td>
                                                                            <td>8.03</td>
                                                                            <td>*0.00</td>
                                                                            <td>25.44</td>
                                                                            <td>33.39</td>
                                                                            <td>*3.75</td>
                                                                            <td>19.37</td>
                                                                            <td>10.18</td>
                                                                            <td>83.92</td>
                                                                            <td>0.00</td>
                                                                            <td>*1.35</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
TOMATO SOUP                                    </td>

                                        <td>90</td>
                                                                            <td>0.00</td>

                                        <td>480.00</td>
                                                                            <td>12.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>1.00</td>
                                                                            <td>2.00</td>
                                                                            <td>8.00</td>
                                                                            <td>0.00</td>
                                                                            <td>10.00</td>
                                                                            <td>4.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
3 BEAN SALAD                                    </td>

                                        <td>90</td>
                                                                            <td>0.00</td>

                                        <td>210.00</td>
                                                                            <td>11.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>17.00</td>
                                                                            <td>2.00</td>
                                                                            <td>2.00</td>
                                                                            <td>200.00</td>
                                                                            <td>40.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLE, RED DELICIOUS                                    </td>

                                        <td>80</td>
                                                                            <td>0.00</td>

                                        <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>7.00</td>
                                                                            <td>22.00</td>
                                                                            <td>4.00</td>
                                                                            <td>2.00</td>
                                                                            <td>100.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.80</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
WELCH&#39;S FRUIT SNACK                                    </td>

                                        <td>95</td>
                                                                            <td>0.00</td>

                                        <td>10.00</td>
                                                                            <td>13.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>24.50</td>
                                                                            <td>0.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1325.00</td>
                                                                            <td>0.00</td>
                                                                            <td>63.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK, 1% LOW FAT WHITE                                    </td>

                                        <td>100</td>
                                                                            <td>1.50</td>

                                        <td>120.00</td>
                                                                            <td>11.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>15.00</td>
                                                                            <td>11.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-04-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Monday, September 4, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-04-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
***HOLIDAY***                                    </td>

                                        <td>*N/A*</td>
                                                                            <td>*N/A*</td>

                                        <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
**NON-ATTENDANCE DAY***                                    </td>

                                        <td>*N/A*</td>
                                                                            <td>*N/A*</td>

                                        <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-05-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Tuesday, September 5, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-05-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
PEPPERONI PIZZA WEDGE                                    </td>

                                        <td>270</td>
                                                                            <td>3.50</td>

                                        <td>860.00</td>
                                                                            <td>5.00</td>
                                                                            <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>15.00</td>
                                                                            <td>32.00</td>
                                                                            <td>4.00</td>
                                                                            <td>16.00</td>
                                                                            <td>10.00</td>
                                                                            <td>25.00</td>
                                                                            <td>0.00</td>
                                                                            <td>10.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE GRAPE PBJ(wheat)                                    </td>

                                        <td>320</td>
                                                                            <td>3.50</td>

                                        <td>320.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>33.00</td>
                                                                            <td>3.00</td>
                                                                            <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
SPINACH/ROMAINE SALAD                                    </td>

                                        <td>43</td>
                                                                            <td>*0.11</td>

                                        <td>*134.38</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.66</td>
                                                                            <td>*N/A*</td>
                                                                            <td>6.00</td>
                                                                            <td>12.17</td>
                                                                            <td>5.74</td>
                                                                            <td>6.86</td>
                                                                            <td>17950.00</td>
                                                                            <td>208.40</td>
                                                                            <td>52.60</td>
                                                                            <td>5.41</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DRESSING, Light                                    </td>

                                        <td>60</td>
                                                                            <td>0.50</td>

                                        <td>370.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>7.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLESAUCE (k)                                    </td>

                                        <td>90</td>
                                                                            <td>0.00</td>

                                        <td>10.00</td>
                                                                            <td>18.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>22.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHOCOLATE CHIP COOKIE                                    </td>

                                        <td>130</td>
                                                                            <td>2.00</td>

                                        <td>70.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>6.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>18.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-06-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Wednesday, September 6, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-06-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
CHICKEN RINGS                                    </td>

                                        <td>304</td>
                                                                            <td>3.17</td>

                                        <td>456.16</td>
                                                                            <td>1.27</td>
                                                                            <td>17.74</td>
                                                                            <td>*N/A*</td>
                                                                            <td>50.68</td>
                                                                            <td>15.21</td>
                                                                            <td>1.27</td>
                                                                            <td>21.54</td>
                                                                            <td>126.71</td>
                                                                            <td>25.34</td>
                                                                            <td>0.00</td>
                                                                            <td>1.82</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP                                    </td>

                                        <td>15</td>
                                                                            <td>*N/A*</td>

                                        <td>190.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>300.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHERRY CRAISINS                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>0.00</td>
                                                                            <td>24.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>28.00</td>
                                                                            <td>3.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
TATER TOTS                                    </td>

                                        <td>107</td>
                                                                            <td>1.33</td>

                                        <td>220.11</td>
                                                                            <td>0.00</td>
                                                                            <td>5.34</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>12.67</td>
                                                                            <td>1.33</td>
                                                                            <td>1.33</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.80</td>
                                                                            <td>0.48</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
WHOLE KERNEL CORN                                    </td>

                                        <td>80</td>
                                                                            <td>*N/A*</td>

                                        <td>140.00</td>
                                                                            <td>4.00</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>17.00</td>
                                                                            <td>2.00</td>
                                                                            <td>2.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.60</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
ORANGE SHERBET CUP                                    </td>

                                        <td>110</td>
                                                                            <td>0.50</td>

                                        <td>15.00</td>
                                                                            <td>22.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>24.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-07-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Thursday, September 7, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-07-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
PHILLY CHEESE STEAK on BUN                                    </td>

                                        <td>368</td>
                                                                            <td>7.46</td>

                                        <td>838.98</td>
                                                                            <td>*2.00</td>
                                                                            <td>15.77</td>
                                                                            <td>0.75</td>
                                                                            <td>54.84</td>
                                                                            <td>30.16</td>
                                                                            <td>0.52</td>
                                                                            <td>26.35</td>
                                                                            <td>143.36</td>
                                                                            <td>233.88</td>
                                                                            <td>0.00</td>
                                                                            <td>2.91</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MASHED POTATO (jhs)                                    </td>

                                        <td>60</td>
                                                                            <td>0.00</td>

                                        <td>25.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>13.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>15.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CARROTS, baby peeled                                    </td>

                                        <td>23</td>
                                                                            <td>*N/A*</td>

                                        <td>26.67</td>
                                                                            <td>3.33</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.33</td>
                                                                            <td>1.33</td>
                                                                            <td>0.67</td>
                                                                            <td>9000.00</td>
                                                                            <td>13.33</td>
                                                                            <td>4.00</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH (jjhs)                                    </td>

                                        <td>120</td>
                                                                            <td>2.00</td>

                                        <td>250.00</td>
                                                                            <td>1.00</td>
                                                                            <td>13.00</td>
                                                                            <td>0.00</td>
                                                                            <td>10.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
FUJI APPLES                                    </td>

                                        <td>40</td>
                                                                            <td>0.00</td>

                                        <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>11.00</td>
                                                                            <td>2.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>500.00</td>
                                                                            <td>10.00</td>
                                                                            <td>6.00</td>
                                                                            <td>0.20</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
OREO COOKIES                                    </td>

                                        <td>100</td>
                                                                            <td>1.00</td>

                                        <td>85.00</td>
                                                                            <td>9.00</td>
                                                                            <td>4.50</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>16.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.10</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-08-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Friday, September 8, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-08-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
SUPER SOFT PRETZEL (jcb)                                    </td>

                                        <td>190</td>
                                                                            <td>*N/A*</td>

                                        <td>160.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>40.00</td>
                                                                            <td>2.00</td>
                                                                            <td>6.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.80</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHEDDAR CHEESE SAUCE                                    </td>

                                        <td>90</td>
                                                                            <td>2.50</td>

                                        <td>470.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>7.00</td>
                                                                            <td>1.50</td>
                                                                            <td>10.00</td>
                                                                            <td>4.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.00</td>
                                                                            <td>100.00</td>
                                                                            <td>100.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BAKED BEANS                                    </td>

                                        <td>315</td>
                                                                            <td>0.00</td>

                                        <td>1237.50</td>
                                                                            <td>27.00</td>
                                                                            <td>2.25</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>65.25</td>
                                                                            <td>11.25</td>
                                                                            <td>13.50</td>
                                                                            <td>0.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>22.50</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
FRUITABLE TROPICAL TWIST                                    </td>

                                        <td>61</td>
                                                                            <td>*N/A*</td>

                                        <td>15.32</td>
                                                                            <td>12.26</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>14.30</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>510.64</td>
                                                                            <td>*N/A*</td>
                                                                            <td>61.28</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
PEARS, SLICED in LIGHT SYRUP                                    </td>

                                        <td>70</td>
                                                                            <td>*N/A*</td>

                                        <td>10.00</td>
                                                                            <td>15.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>17.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-11-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Monday, September 11, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-11-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
FRENCH TOAST STICKS (wg)                                    </td>

                                        <td>310</td>
                                                                            <td>3.00</td>

                                        <td>410.00</td>
                                                                            <td>14.00</td>
                                                                            <td>12.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>45.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>1.80</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
SYRUP CUP                                    </td>

                                        <td>120</td>
                                                                            <td>0.00</td>

                                        <td>0.00</td>
                                                                            <td>19.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>31.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE GRAPE PBJ(wheat)                                    </td>

                                        <td>320</td>
                                                                            <td>3.50</td>

                                        <td>320.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>33.00</td>
                                                                            <td>3.00</td>
                                                                            <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
PORK SAUSAGE PATTY                                    </td>

                                        <td>120</td>
                                                                            <td>4.00</td>

                                        <td>190.00</td>
                                                                            <td>0.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>4.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
TRI-TATORS                                    </td>

                                        <td>93</td>
                                                                            <td>1.00</td>

                                        <td>193.43</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.67</td>
                                                                            <td>1.67</td>
                                                                            <td>*N/A*</td>
                                                                            <td>11.34</td>
                                                                            <td>1.33</td>
                                                                            <td>0.67</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>2.40</td>
                                                                            <td>0.27</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP                                    </td>

                                        <td>15</td>
                                                                            <td>*N/A*</td>

                                        <td>190.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>300.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHERRY TOMATOES                                    </td>

                                        <td>18</td>
                                                                            <td>*N/A*</td>

                                        <td>3.75</td>
                                                                            <td>3.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.50</td>
                                                                            <td>1.50</td>
                                                                            <td>0.75</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.27</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
ORANGES                                    </td>

                                        <td>40</td>
                                                                            <td>0.00</td>

                                        <td>0.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>10.50</td>
                                                                            <td>2.00</td>
                                                                            <td>1.00</td>
                                                                            <td>200.00</td>
                                                                            <td>30.00</td>
                                                                            <td>48.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-12-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Tuesday, September 12, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-12-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
FRENCH BREAD GARLIC PIZZA                                    </td>

                                        <td>330</td>
                                                                            <td>6.00</td>

                                        <td>700.00</td>
                                                                            <td>2.00</td>
                                                                            <td>16.00</td>
                                                                            <td>0.00</td>
                                                                            <td>20.00</td>
                                                                            <td>30.00</td>
                                                                            <td>3.00</td>
                                                                            <td>17.00</td>
                                                                            <td>500.00</td>
                                                                            <td>350.00</td>
                                                                            <td>0.00</td>
                                                                            <td>1.80</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BROCCOLI FLORETS                                    </td>

                                        <td>6</td>
                                                                            <td>0.00</td>

                                        <td>7.34</td>
                                                                            <td>0.40</td>
                                                                            <td>0.07</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>1.07</td>
                                                                            <td>0.67</td>
                                                                            <td>0.67</td>
                                                                            <td>100.05</td>
                                                                            <td>8.00</td>
                                                                            <td>17.61</td>
                                                                            <td>0.14</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DRESSING, Light                                    </td>

                                        <td>60</td>
                                                                            <td>0.50</td>

                                        <td>370.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>7.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLE, RED DELICIOUS                                    </td>

                                        <td>80</td>
                                                                            <td>0.00</td>

                                        <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>7.00</td>
                                                                            <td>22.00</td>
                                                                            <td>4.00</td>
                                                                            <td>2.00</td>
                                                                            <td>100.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.80</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
NUTTY BUDDY (wafer cookie)                                    </td>

                                        <td>100</td>
                                                                            <td>3.00</td>

                                        <td>35.00</td>
                                                                            <td>7.00</td>
                                                                            <td>6.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>11.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>35.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-13-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Wednesday, September 13, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-13-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
POPCORN CHICKEN                                    </td>

                                        <td>230</td>
                                                                            <td>2.50</td>

                                        <td>350.00</td>
                                                                            <td>1.00</td>
                                                                            <td>13.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>14.00</td>
                                                                            <td>2.00</td>
                                                                            <td>14.00</td>
                                                                            <td>100.00</td>
                                                                            <td>40.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BBQ SAUCE CUP                                    </td>

                                        <td>30</td>
                                                                            <td>0.00</td>

                                        <td>160.00</td>
                                                                            <td>6.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>7.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>50.00</td>
                                                                            <td>0.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.18</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KRINKLE KUT FRIES                                    </td>

                                        <td>107</td>
                                                                            <td>0.33</td>

                                        <td>153.41</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.68</td>
                                                                            <td>1.33</td>
                                                                            <td>1.33</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.47</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP PACKET                                    </td>

                                        <td>10</td>
                                                                            <td>0.00</td>

                                        <td>25.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CARROTS,BABY PEELED                                    </td>

                                        <td>40</td>
                                                                            <td>*N/A*</td>

                                        <td>90.00</td>
                                                                            <td>8.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>10.00</td>
                                                                            <td>2.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>8000.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DRESSING, Light                                    </td>

                                        <td>60</td>
                                                                            <td>0.50</td>

                                        <td>370.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>7.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
PINEAPPLE/MANDARIN MIX                                    </td>

                                        <td>71</td>
                                                                            <td>0.01</td>

                                        <td>3.40</td>
                                                                            <td>*7.50</td>
                                                                            <td>0.08</td>
                                                                            <td>*0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>18.11</td>
                                                                            <td>1.18</td>
                                                                            <td>0.31</td>
                                                                            <td>733.68</td>
                                                                            <td>4.54</td>
                                                                            <td>18.61</td>
                                                                            <td>1.21</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-14-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Thursday, September 14, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-14-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
CHEESEBURGER on BUN                                    </td>

                                        <td>351</td>
                                                                            <td>8.86</td>

                                        <td>468.76</td>
                                                                            <td>*0.68</td>
                                                                            <td>21.68</td>
                                                                            <td>*1.00</td>
                                                                            <td>75.18</td>
                                                                            <td>14.57</td>
                                                                            <td>*0.27</td>
                                                                            <td>23.86</td>
                                                                            <td>4.07</td>
                                                                            <td>49.55</td>
                                                                            <td>0.00</td>
                                                                            <td>*2.51</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP PACKET                                    </td>

                                        <td>10</td>
                                                                            <td>0.00</td>

                                        <td>25.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MUSTARD                                    </td>

                                        <td>5</td>
                                                                            <td>*N/A*</td>

                                        <td>50.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE GRAPE PBJ(wheat)                                    </td>

                                        <td>320</td>
                                                                            <td>3.50</td>

                                        <td>320.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>33.00</td>
                                                                            <td>3.00</td>
                                                                            <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KRINKLE KUT FRIES                                    </td>

                                        <td>107</td>
                                                                            <td>0.33</td>

                                        <td>153.41</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.68</td>
                                                                            <td>1.33</td>
                                                                            <td>1.33</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.47</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BABY CARROTS (RAW)                                    </td>

                                        <td>23</td>
                                                                            <td>*N/A*</td>

                                        <td>26.67</td>
                                                                            <td>3.33</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.33</td>
                                                                            <td>1.33</td>
                                                                            <td>0.67</td>
                                                                            <td>9000.00</td>
                                                                            <td>13.33</td>
                                                                            <td>4.00</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DRESSING, Light                                    </td>

                                        <td>60</td>
                                                                            <td>0.50</td>

                                        <td>370.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>7.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLE SLICES                                    </td>

                                        <td>50</td>
                                                                            <td>*N/A*</td>

                                        <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.00</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
DILL PICKLE SPEAR                                    </td>

                                        <td>3</td>
                                                                            <td>*N/A*</td>

                                        <td>428.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.70</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.20</td>
                                                                            <td>3.00</td>
                                                                            <td>8.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-15-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Friday, September 15, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-15-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
MINI CORN DOGS                                    </td>

                                        <td>250</td>
                                                                            <td>1.50</td>

                                        <td>630.00</td>
                                                                            <td>8.00</td>
                                                                            <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>15.00</td>
                                                                            <td>31.00</td>
                                                                            <td>1.00</td>
                                                                            <td>11.00</td>
                                                                            <td>40.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.60</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP PACKET                                    </td>

                                        <td>10</td>
                                                                            <td>0.00</td>

                                        <td>25.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MUSTARD                                    </td>

                                        <td>5</td>
                                                                            <td>*N/A*</td>

                                        <td>50.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BAKED BEANS                                    </td>

                                        <td>210</td>
                                                                            <td>0.00</td>

                                        <td>825.00</td>
                                                                            <td>18.00</td>
                                                                            <td>1.50</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>43.50</td>
                                                                            <td>7.50</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>6.00</td>
                                                                            <td>0.00</td>
                                                                            <td>15.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
FRUITABLE TROPICAL TWIST                                    </td>

                                        <td>61</td>
                                                                            <td>*N/A*</td>

                                        <td>15.32</td>
                                                                            <td>12.26</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>14.30</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>510.64</td>
                                                                            <td>*N/A*</td>
                                                                            <td>61.28</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
STRAWBERRY APPLESAUCE CUP                                    </td>

                                        <td>100</td>
                                                                            <td>*N/A*</td>

                                        <td>25.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>23.00</td>
                                                                            <td>2.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.20</td>
                                                                            <td>0.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHIPS AHOY 100 Calorie Pak                                    </td>

                                        <td>100</td>
                                                                            <td>0.50</td>

                                        <td>140.00</td>
                                                                            <td>7.00</td>
                                                                            <td>3.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>18.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.72</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-18-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Monday, September 18, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-18-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
CHEDDAR CHEESE OMELETTE                                    </td>

                                        <td>210</td>
                                                                            <td>7.00</td>

                                        <td>520.00</td>
                                                                            <td>2.00</td>
                                                                            <td>16.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>260.00</td>
                                                                            <td>4.00</td>
                                                                            <td>0.00</td>
                                                                            <td>12.00</td>
                                                                            <td>600.00</td>
                                                                            <td>150.00</td>
                                                                            <td>0.00</td>
                                                                            <td>1.08</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
ENGLISH MUFFIN                                    </td>

                                        <td>62</td>
                                                                            <td>0.00</td>

                                        <td>114.24</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.48</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>12.38</td>
                                                                            <td>0.48</td>
                                                                            <td>2.38</td>
                                                                            <td>0.00</td>
                                                                            <td>71.40</td>
                                                                            <td>0.00</td>
                                                                            <td>0.86</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
HASH BROWN PATTY                                    </td>

                                        <td>117</td>
                                                                            <td>1.80</td>

                                        <td>207.23</td>
                                                                            <td>*N/A*</td>
                                                                            <td>7.21</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.61</td>
                                                                            <td>1.80</td>
                                                                            <td>0.90</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.32</td>
                                                                            <td>0.32</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP PACKET                                    </td>

                                        <td>10</td>
                                                                            <td>0.00</td>

                                        <td>25.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CARROTEENIES                                    </td>

                                        <td>56</td>
                                                                            <td>*N/A*</td>

                                        <td>131.25</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>15.00</td>
                                                                            <td>3.75</td>
                                                                            <td>*N/A*</td>
                                                                            <td>11250.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DIPPING CUP 1 OZ                                    </td>

                                        <td>130</td>
                                                                            <td>2.00</td>

                                        <td>270.00</td>
                                                                            <td>2.00</td>
                                                                            <td>13.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>3.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
ORANGE WEDGES                                    </td>

                                        <td>55</td>
                                                                            <td>0.00</td>

                                        <td>0.00</td>
                                                                            <td>9.66</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>14.49</td>
                                                                            <td>2.76</td>
                                                                            <td>1.38</td>
                                                                            <td>276.00</td>
                                                                            <td>41.40</td>
                                                                            <td>66.24</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-19-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Tuesday, September 19, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-19-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
BOSCO BREADSTICK                                    </td>

                                        <td>284</td>
                                                                            <td>4.05</td>

                                        <td>364.77</td>
                                                                            <td>2.70</td>
                                                                            <td>8.11</td>
                                                                            <td>0.00</td>
                                                                            <td>20.26</td>
                                                                            <td>33.78</td>
                                                                            <td>2.70</td>
                                                                            <td>16.21</td>
                                                                            <td>270.20</td>
                                                                            <td>270.20</td>
                                                                            <td>0.00</td>
                                                                            <td>1.94</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MARINARA SAUCE                                    </td>

                                        <td>30</td>
                                                                            <td>0.00</td>

                                        <td>245.00</td>
                                                                            <td>2.50</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>4.50</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>250.00</td>
                                                                            <td>10.00</td>
                                                                            <td>4.50</td>
                                                                            <td>0.54</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CUCUMBER SLICES                                    </td>

                                        <td>15</td>
                                                                            <td>*N/A*</td>

                                        <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DRESSING, Light                                    </td>

                                        <td>60</td>
                                                                            <td>0.50</td>

                                        <td>370.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>7.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
STRAWBERRY APPLESAUCE CUP                                    </td>

                                        <td>100</td>
                                                                            <td>*N/A*</td>

                                        <td>25.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>23.00</td>
                                                                            <td>2.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.20</td>
                                                                            <td>0.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHOCOLATE CHIP COOKIE (wg)                                    </td>

                                        <td>110</td>
                                                                            <td>1.00</td>

                                        <td>85.00</td>
                                                                            <td>8.00</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>18.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>10.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>15.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-20-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Wednesday, September 20, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-20-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
CHICKEN DRUMSTICK                                    </td>

                                        <td>190</td>
                                                                            <td>2.50</td>

                                        <td>450.00</td>
                                                                            <td>0.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>50.00</td>
                                                                            <td>5.00</td>
                                                                            <td>1.00</td>
                                                                            <td>16.00</td>
                                                                            <td>2.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>6.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
EMOJI FRIES                                    </td>

                                        <td>130</td>
                                                                            <td>0.50</td>

                                        <td>180.00</td>
                                                                            <td>0.00</td>
                                                                            <td>4.50</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>20.00</td>
                                                                            <td>2.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.40</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP CUP                                    </td>

                                        <td>30</td>
                                                                            <td>0.00</td>

                                        <td>75.00</td>
                                                                            <td>5.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>7.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>100.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
PEAPODS                                    </td>

                                        <td>30</td>
                                                                            <td>*N/A*</td>

                                        <td>*N/A*</td>
                                                                            <td>2.67</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>2.00</td>
                                                                            <td>2.00</td>
                                                                            <td>13.33</td>
                                                                            <td>4.00</td>
                                                                            <td>20.00</td>
                                                                            <td>4.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DIPPING CUP 1 OZ                                    </td>

                                        <td>130</td>
                                                                            <td>2.00</td>

                                        <td>270.00</td>
                                                                            <td>2.00</td>
                                                                            <td>13.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>3.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLE SLICES                                    </td>

                                        <td>50</td>
                                                                            <td>*N/A*</td>

                                        <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.00</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHOCOLATE PUDDING                                    </td>

                                        <td>60</td>
                                                                            <td>0.25</td>

                                        <td>80.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>0.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.40</td>
                                                                            <td>*N/A*</td>
                                                                            <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.20</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-21-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Thursday, September 21, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-21-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
SPAGHETTI &amp; MEATBALLS (rw)                                    </td>

                                        <td>235</td>
                                                                            <td>2.74</td>

                                        <td>587.50</td>
                                                                            <td>*6.75</td>
                                                                            <td>7.11</td>
                                                                            <td>0.00</td>
                                                                            <td>15.00</td>
                                                                            <td>33.14</td>
                                                                            <td>4.63</td>
                                                                            <td>10.34</td>
                                                                            <td>595.83</td>
                                                                            <td>53.17</td>
                                                                            <td>26.67</td>
                                                                            <td>3.43</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
GARLIC TOAST                                    </td>

                                        <td>160</td>
                                                                            <td>2.00</td>

                                        <td>280.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>15.00</td>
                                                                            <td>1.00</td>
                                                                            <td>3.00</td>
                                                                            <td>200.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BROCCOLI FLORETS (fresh)                                    </td>

                                        <td>36</td>
                                                                            <td>0.00</td>

                                        <td>44.00</td>
                                                                            <td>2.40</td>
                                                                            <td>0.40</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>6.40</td>
                                                                            <td>4.00</td>
                                                                            <td>4.00</td>
                                                                            <td>600.00</td>
                                                                            <td>48.00</td>
                                                                            <td>105.60</td>
                                                                            <td>0.86</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DRESSING, Light                                    </td>

                                        <td>60</td>
                                                                            <td>0.50</td>

                                        <td>370.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>7.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
FRUIT COCKTAIL                                    </td>

                                        <td>60</td>
                                                                            <td>0.00</td>

                                        <td>10.00</td>
                                                                            <td>14.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>15.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>200.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.40</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-22-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Friday, September 22, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-22-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
HAM &amp; AMERICAN SANDWICH                                    </td>

                                        <td>308</td>
                                                                            <td>6.66</td>

                                        <td>1093.30</td>
                                                                            <td>*1.00</td>
                                                                            <td>12.48</td>
                                                                            <td>*0.00</td>
                                                                            <td>57.00</td>
                                                                            <td>26.79</td>
                                                                            <td>2.86</td>
                                                                            <td>22.10</td>
                                                                            <td>*272.00</td>
                                                                            <td>*185.90</td>
                                                                            <td>*0.00</td>
                                                                            <td>2.13</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MAYONNAISE PACKETS                                    </td>

                                        <td>80</td>
                                                                            <td>1.50</td>

                                        <td>75.00</td>
                                                                            <td>1.00</td>
                                                                            <td>8.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MUSTARD (offered)                                    </td>

                                        <td>*N/A*</td>
                                                                            <td>*N/A*</td>

                                        <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
TINY TWIST PRETZELS                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>450.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>23.00</td>
                                                                            <td>1.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>6.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
HUMMUS                                    </td>

                                        <td>182</td>
                                                                            <td>1.44</td>

                                        <td>301.25</td>
                                                                            <td>*N/A*</td>
                                                                            <td>7.90</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>22.38</td>
                                                                            <td>4.38</td>
                                                                            <td>7.49</td>
                                                                            <td>21.25</td>
                                                                            <td>37.50</td>
                                                                            <td>7.75</td>
                                                                            <td>1.38</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CELERY STICKS                                    </td>

                                        <td>18</td>
                                                                            <td>*N/A*</td>

                                        <td>100.30</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.10</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.10</td>
                                                                            <td>0.80</td>
                                                                            <td>0.80</td>
                                                                            <td>145.00</td>
                                                                            <td>41.00</td>
                                                                            <td>7.20</td>
                                                                            <td>0.60</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
3 BEAN SALAD                                    </td>

                                        <td>135</td>
                                                                            <td>0.00</td>

                                        <td>315.00</td>
                                                                            <td>16.50</td>
                                                                            <td>1.50</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>25.50</td>
                                                                            <td>3.00</td>
                                                                            <td>3.00</td>
                                                                            <td>300.00</td>
                                                                            <td>60.00</td>
                                                                            <td>1.80</td>
                                                                            <td>0.54</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MANDARIN ORANGE, whole segment                                    </td>

                                        <td>90</td>
                                                                            <td>0.00</td>

                                        <td>10.00</td>
                                                                            <td>19.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>1.00</td>
                                                                            <td>400.00</td>
                                                                            <td>20.00</td>
                                                                            <td>18.00</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RICE KRISPIE TREAT                                    </td>

                                        <td>90</td>
                                                                            <td>0.50</td>

                                        <td>105.00</td>
                                                                            <td>8.00</td>
                                                                            <td>2.25</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>12.50</td>
                                                                            <td>0.00</td>
                                                                            <td>0.50</td>
                                                                            <td>4.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-25-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Monday, September 25, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-25-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
SAUSAGE, EGG AND CHEESE MUFFIN                                    </td>

                                        <td>367</td>
                                                                            <td>6.96</td>

                                        <td>821.26</td>
                                                                            <td>*0.68</td>
                                                                            <td>20.36</td>
                                                                            <td>*0.00</td>
                                                                            <td>139.93</td>
                                                                            <td>28.46</td>
                                                                            <td>*1.00</td>
                                                                            <td>17.06</td>
                                                                            <td>168.31</td>
                                                                            <td>180.35</td>
                                                                            <td>0.01</td>
                                                                            <td>*4.18</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
V8 JUICE                                    </td>

                                        <td>30</td>
                                                                            <td>0.00</td>

                                        <td>95.00</td>
                                                                            <td>5.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>7.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>25.00</td>
                                                                            <td>2.00</td>
                                                                            <td>80.00</td>
                                                                            <td>2.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
STRAWBERRY YOGURT CUP(danimal)                                    </td>

                                        <td>80</td>
                                                                            <td>0.00</td>

                                        <td>65.00</td>
                                                                            <td>13.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>16.00</td>
                                                                            <td>0.00</td>
                                                                            <td>4.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CHERRY CRAISINS                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>0.00</td>
                                                                            <td>24.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>28.00</td>
                                                                            <td>3.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
WELCH&#39;S FRUIT SNACK                                    </td>

                                        <td>95</td>
                                                                            <td>0.00</td>

                                        <td>10.00</td>
                                                                            <td>13.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>24.50</td>
                                                                            <td>0.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1325.00</td>
                                                                            <td>0.00</td>
                                                                            <td>63.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-26-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Tuesday, September 26, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-26-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
PERSONAL CHEESE PIZZA                                    </td>

                                        <td>315</td>
                                                                            <td>3.45</td>

                                        <td>600.85</td>
                                                                            <td>4.92</td>
                                                                            <td>10.84</td>
                                                                            <td>0.00</td>
                                                                            <td>9.85</td>
                                                                            <td>42.36</td>
                                                                            <td>4.92</td>
                                                                            <td>16.74</td>
                                                                            <td>5.91</td>
                                                                            <td>24.62</td>
                                                                            <td>0.00</td>
                                                                            <td>14.78</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
SPINACH/ROMAINE SALAD                                    </td>

                                        <td>43</td>
                                                                            <td>*0.11</td>

                                        <td>*134.38</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.66</td>
                                                                            <td>*N/A*</td>
                                                                            <td>6.00</td>
                                                                            <td>12.17</td>
                                                                            <td>5.74</td>
                                                                            <td>6.86</td>
                                                                            <td>17950.00</td>
                                                                            <td>208.40</td>
                                                                            <td>52.60</td>
                                                                            <td>5.41</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
ITALIAN DRESSING(NEW)                                    </td>

                                        <td>62</td>
                                                                            <td>0.92</td>

                                        <td>4.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>6.56</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.95</td>
                                                                            <td>0.10</td>
                                                                            <td>0.08</td>
                                                                            <td>169.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.20</td>
                                                                            <td>0.08</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLE, RED DELICIOUS                                    </td>

                                        <td>80</td>
                                                                            <td>0.00</td>

                                        <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>7.00</td>
                                                                            <td>22.00</td>
                                                                            <td>4.00</td>
                                                                            <td>2.00</td>
                                                                            <td>100.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.80</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
JELLO-STRAWBERRY                                    </td>

                                        <td>70</td>
                                                                            <td>*N/A*</td>

                                        <td>80.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>17.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>15.00</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-27-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Wednesday, September 27, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-27-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
CHICKEN NUGGETS                                    </td>

                                        <td>197</td>
                                                                            <td>2.06</td>

                                        <td>386.34</td>
                                                                            <td>0.82</td>
                                                                            <td>11.51</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.44</td>
                                                                            <td>13.15</td>
                                                                            <td>2.47</td>
                                                                            <td>10.69</td>
                                                                            <td>82.20</td>
                                                                            <td>32.88</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.48</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BREAD &amp; BUTTER (rw)                                    </td>

                                        <td>59</td>
                                                                            <td>0.00</td>

                                        <td>117.74</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.49</td>
                                                                            <td>*0.00</td>
                                                                            <td>*0.00</td>
                                                                            <td>*11.77</td>
                                                                            <td>*1.47</td>
                                                                            <td>*2.94</td>
                                                                            <td>0.00</td>
                                                                            <td>*19.62</td>
                                                                            <td>*0.00</td>
                                                                            <td>*0.53</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KRINKLE KUT FRIES                                    </td>

                                        <td>107</td>
                                                                            <td>0.33</td>

                                        <td>153.41</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>16.68</td>
                                                                            <td>1.33</td>
                                                                            <td>1.33</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.47</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP PACKET                                    </td>

                                        <td>10</td>
                                                                            <td>0.00</td>

                                        <td>25.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CARROTS,BABY PEELED                                    </td>

                                        <td>40</td>
                                                                            <td>*N/A*</td>

                                        <td>90.00</td>
                                                                            <td>8.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>10.00</td>
                                                                            <td>2.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>8000.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
RANCH DRESSING, Light                                    </td>

                                        <td>60</td>
                                                                            <td>0.50</td>

                                        <td>370.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>3.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>5.00</td>
                                                                            <td>7.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLE JUICE-100%                                    </td>

                                        <td>50</td>
                                                                            <td>0.00</td>

                                        <td>0.00</td>
                                                                            <td>12.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>13.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>60.00</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-28-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Thursday, September 28, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-28-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
BEEF HOT DOG on BUN                                    </td>

                                        <td>336</td>
                                                                            <td>6.00</td>

                                        <td>820.62</td>
                                                                            <td>*0.00</td>
                                                                            <td>18.97</td>
                                                                            <td>0.50</td>
                                                                            <td>35.00</td>
                                                                            <td>31.88</td>
                                                                            <td>0.00</td>
                                                                            <td>10.75</td>
                                                                            <td>*0.00</td>
                                                                            <td>47.50</td>
                                                                            <td>*0.00</td>
                                                                            <td>2.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
KETCHUP                                    </td>

                                        <td>15</td>
                                                                            <td>*N/A*</td>

                                        <td>190.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>300.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MUSTARD                                    </td>

                                        <td>5</td>
                                                                            <td>*N/A*</td>

                                        <td>50.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.50</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
BAKED BEANS                                    </td>

                                        <td>210</td>
                                                                            <td>0.00</td>

                                        <td>825.00</td>
                                                                            <td>18.00</td>
                                                                            <td>1.50</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>43.50</td>
                                                                            <td>7.50</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>6.00</td>
                                                                            <td>0.00</td>
                                                                            <td>15.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
FRUITABLE PLUS POWER PUNCH                                    </td>

                                        <td>61</td>
                                                                            <td>*N/A*</td>

                                        <td>15.32</td>
                                                                            <td>12.26</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>14.30</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>510.64</td>
                                                                            <td>*N/A*</td>
                                                                            <td>61.28</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
PEACHES, sliced in light syrup                                    </td>

                                        <td>70</td>
                                                                            <td>*N/A*</td>

                                        <td>10.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>17.00</td>
                                                                            <td>1.00</td>
                                                                            <td>1.00</td>
                                                                            <td>300.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.20</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>
                    <div data-role="page" id="Nutrients-09-29-2017">
                    <div data-role="header" data-theme="b">
                        <h1>Nutrients</h1>
                    </div>

                    <div role="main" class="ui-content">
                        <h2>Friday, September 29, 2017</h2>

                        <table data-role="table" data-mode="reflow" class="NutrientTable" id="NutrientTable-09-29-2017">
                            <thead>
                            <tr>
                                <th class="NutrientTableRecipeColumn"><abbr title="Recipe">Recipes</abbr></th>
                                    <th><abbr title="Calories (kcal)">Calories<br/>(kcal)</abbr></th>
                                                                    <th><abbr title="Saturated Fat (g)">Sat Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Sodium (mg)">Sodium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Sugars (g)">Sugars <br/> (g)</abbr></th>
                                                                    <th><abbr title="Total Fat (g)">Total Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Trans Fat (g)">Trans Fat <br/> (g)</abbr></th>
                                                                    <th><abbr title="Cholesterol (mg)">Chol <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Carbohydrates (g)">Carbs <br/> (g)</abbr></th>
                                                                    <th><abbr title="Dietary Fiber (g)">Fiber <br/> (g)</abbr></th>
                                                                    <th><abbr title="Protein (g)">Protein <br/> (g)</abbr></th>
                                                                    <th><abbr title="Vitamin A (IU)">Vit-A <br/> (IU)</abbr></th>
                                                                    <th><abbr title="Calcium (mg)">Calcium <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Vitamin C (mg)">Vit-C <br/> (mg)</abbr></th>
                                                                    <th><abbr title="Iron (mg)">Iron <br/> (mg)</abbr></th>
                            </tr>
                            </thead>
                            <tbody>

                                <tr>
                                    <td class="nutrientTableRecipeName">
MACARONI &amp; CHEESE                                    </td>

                                        <td>350</td>
                                                                            <td>13.00</td>

                                        <td>900.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>22.00</td>
                                                                            <td>1.00</td>
                                                                            <td>60.00</td>
                                                                            <td>22.00</td>
                                                                            <td>1.00</td>
                                                                            <td>16.00</td>
                                                                            <td>750.00</td>
                                                                            <td>450.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
UNCRUSTABLE, GRAPE whole wheat                                    </td>

                                        <td>300</td>
                                                                            <td>3.00</td>

                                        <td>280.00</td>
                                                                            <td>14.00</td>
                                                                            <td>11.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>3.00</td>
                                                                            <td>4.00</td>
                                                                            <td>9.00</td>
                                                                            <td>0.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
APPLE, RED DELICIOUS                                    </td>

                                        <td>80</td>
                                                                            <td>0.00</td>

                                        <td>*N/A*</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>7.00</td>
                                                                            <td>22.00</td>
                                                                            <td>4.00</td>
                                                                            <td>2.00</td>
                                                                            <td>100.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>4.80</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
GARLIC CHEDDAR BISCUIT                                    </td>

                                        <td>100</td>
                                                                            <td>2.50</td>

                                        <td>390.00</td>
                                                                            <td>2.00</td>
                                                                            <td>5.00</td>
                                                                            <td>2.00</td>
                                                                            <td>0.00</td>
                                                                            <td>12.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>2.00</td>
                                                                            <td>100.00</td>
                                                                            <td>0.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.36</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
CUCUMBER SLICES                                    </td>

                                        <td>22</td>
                                                                            <td>*N/A*</td>

                                        <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
NUTTY BUDDY (wafer cookie)                                    </td>

                                        <td>100</td>
                                                                            <td>3.00</td>

                                        <td>35.00</td>
                                                                            <td>7.00</td>
                                                                            <td>6.00</td>
                                                                            <td>0.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>11.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>1.00</td>
                                                                            <td>35.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.40</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,1% Lowfat WHITE                                    </td>

                                        <td>102</td>
                                                                            <td>1.54</td>

                                        <td>107.36</td>
                                                                            <td>12.69</td>
                                                                            <td>2.37</td>
                                                                            <td>*N/A*</td>
                                                                            <td>12.20</td>
                                                                            <td>12.18</td>
                                                                            <td>0.00</td>
                                                                            <td>8.22</td>
                                                                            <td>478.24</td>
                                                                            <td>305.00</td>
                                                                            <td>0.00</td>
                                                                            <td>0.07</td>
                                </tr>
                                <tr>
                                    <td class="nutrientTableRecipeName">
MILK,Fat Free CHOCOLATE                                    </td>

                                        <td>110</td>
                                                                            <td>0.00</td>

                                        <td>180.00</td>
                                                                            <td>*N/A*</td>
                                                                            <td>0.00</td>
                                                                            <td>0.00</td>
                                                                            <td>5.00</td>
                                                                            <td>20.00</td>
                                                                            <td>0.00</td>
                                                                            <td>8.00</td>
                                                                            <td>500.00</td>
                                                                            <td>300.00</td>
                                                                            <td>1.20</td>
                                                                            <td>0.00</td>
                                </tr>
                            </tbody>
                        </table>

                        <p>
                            <a href="#one" data-rel="back" class="ui-btn ui-shadow ui-corner-all ui-btn-inline ui-icon-back ui-btn-icon-left">Close Nutrients</a>
                        </p>
                    </div>

                    <div data-role="footer">
                        <P style="font-size: 11px; font-family: Arial;">
                                *N/A* - denotes a nutrient that is either missing or incomplete for an individual ingredient<br/>
                                * - denotes combined nutrient totals with either missing or incomplete nutrient data<br/>
                                                        <br/>
                            <br/>
                        </P>
                    </div>

                    </div>

</body>



</html>
