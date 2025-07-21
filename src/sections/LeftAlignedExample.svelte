<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    /* CSS HEX */
//  --eastern-blue: #1e81b0;
// --green-white: #eeeee4;
// --burnt-sienna: #e28743;
// --tacao: #eab676;
// --glacier: #76b5c5;
// --eternity: #21130d;
// --burnt-umber: #873e23;
// --powder-blue: #abdbe3;
// --catalina-blue: #063970;
// --chathams-blue: #154c79;

    const series = [
        {
            name: "Black",
            data: [
                [1972, 10.4],
                [1973, 9.4],
                [1974, 10.5],
                [1975, 14.8],
                [1976, 14],
                [1977, 14],
                [1978, 12.8],
                [1979, 12.3],
                [1980, 14.3],
                [1981, 15.6],
                [1982, 18.9],
                [1983, 19.5],
                [1984, 15.9],
                [1985, 15.1],
                [1986, 14.5],
                [1987, 13],
                [1988, 11.7],
                [1989, 11.4],
                [1990, 11.4],
                [1991, 12.5],
                [1992, 14.2],
                [1993, 13],
                [1994, 11.5],
                [1995, 10.4],
                [1996, 10.5],
                [1997, 10],
                [1998, 8.9],
                [1999, 8],
                [2000, 7.6],
                [2001, 8.6],
                [2002, 10.2],
                [2003, 10.8],
                [2004, 10.4],
                [2005, 10],
                [2006, 8.9],
                [2007, 8.3],
                [2008, 10.1],
                [2009, 14.8],
                [2010, 16],
                [2011, 15.8],
                [2012, 13.8],
                [2013, 13.1],
                [2014, 11.3],
                [2015, 9.6],
                [2016, 8.4],
                [2017, 7.5],
                [2018, 6.5],
                [2019, 6.1],
            ],
            color: "#8427c9",
        },
        {
            name: "White",
            data: [
                [1972, 5.1],
                [1973, 4.3],
                [1974, 5],
                [1975, 7.8],
                [1976, 7],
                [1977, 6.2],
                [1978, 5.2],
                [1979, 5.1],
                [1980, 6.3],
                [1981, 6.7],
                [1982, 8.6],
                [1983, 8.4],
                [1984, 6.5],
                [1985, 6.2],
                [1986, 6],
                [1987, 5.3],
                [1988, 4.7],
                [1989, 4.5],
                [1990, 4.8],
                [1991, 6.1],
                [1992, 6.6],
                [1993, 6.1],
                [1994, 5.3],
                [1995, 4.9],
                [1996, 4.7],
                [1997, 4.2],
                [1998, 3.9],
                [1999, 3.7],
                [2000, 3.5],
                [2001, 4.2],
                [2002, 5.1],
                [2003, 5.2],
                [2004, 4.8],
                [2005, 4.4],
                [2006, 4],
                [2007, 4.1],
                [2008, 5.2],
                [2009, 8.5],
                [2010, 8.7],
                [2011, 7.9],
                [2012, 7.2],
                [2013, 6.5],
                [2014, 5.3],
                [2015, 4.6],
                [2016, 4.3],
                [2017, 3.8],
                [2018, 3.5],
                [2019, 3],
            ],
            color: "#ff99fc",
        },
    ];

    let chart;
    let thirdSeriesVisible = false;

    let options = {
        chart: {
            type: "spline",
            backgroundColor: "#76b5c5",
            // borderColor: "#007052",
            // borderWidth: 5,
            // borderRadius: 20,
        },
        title: {
            text: "Unemployment rate by race, 1972 - 2019",
        },
        subtitle: {
            text: "Subtitle",
        },

        yAxis: {
            title: {
                text: "Employment Rate",
            },
            min: 0,
            max: 25,
            tickInterval: 5,
            labels: {
                format: "{value}%",
            },
        },

        xAxis: {
            title: {
                text: "Year",
                style: {
                    fontSize: "14px",
                    color: "#333",
                },
            },
            tickInterval: 5,
            labels: {
                rotation: -90,
                align: "right",
                y: 10,
                style: {
                    fontSize: "11px",
                    color: "#333",
                },
            },
            min: 1972,
            max: 2017,
            tickPositions: [
                1972, 1977, 1982, 1987, 1992, 1997, 2002, 2007, 2012, 2017,
            ],
        },

        series: [series[0], series[1]],
    };

    function toggleThirdSeries() {
        const existingSeries = chart.series.find((s) => s.name === "Group 3");

        if (existingSeries) {
            existingSeries.remove();
            thirdSeriesVisible = false;
        } else {
            chart.addSeries(series[2]);
            thirdSeriesVisible = true;
        }
    }
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div class="chart">
                <Chart bind:chart {options} highcharts={Highcharts} />
                <div class="chart-footnote">
                    X-axis: Years of recorded business data (1972–2020)
                    <br />
                    Source: <a href="https://example.com">U.S. Census Bureau</a>
                </div>
            </div>
            <!-- <button on:click={toggleThirdSeries} class="toggle-button">
                {thirdSeriesVisible ? "Remove Group 3" : "Add Group 3"}
            </button> -->
            <div>
               
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <p>For decades, there has been an uneven landscape of American business ownership for Black entrepreneurs. 
                    It was only until 1954 when the Bureau of Labor Statistics reported employment rates by race, 
                    of white or nonwhite.</p>

                <p>There is a long-standing disparity of unemployment that exists between black and white workers; 
                Since 1972, the unemployment ratio of black to white workers is 2:1, including in 2019.</p>
            
                <p>This means black workers are twice as likely to be unemployed than white workers.</p>
            </ArticleText>

            <ArticleText>
                <p>It’s important to point out the undercapitalization of Black businesses 
                    in regards to the U.S metro area’s Black populations. If the number of Black 
                    businesses matched population size and employees per firm matched the average business, 
                    it would create 206,441 jobs.</p>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .chart {
        width: 100%;
        margin: 0px auto;
    }

    .chart-footnote {
        font-size: 12px;
        color: #666;
        text-align: right;
        margin-top: 8px;
        line-height: 1.4;
    }

    /* .toggle-button {
        margin: 20px;
        padding: 20px;
        color: #007052;
        background-color: #0bd956;
        border: solid 2px #007052;
        border-radius: 16px;
        font-size: large;
        cursor: pointer;
        transition: all 0.2s ease;
        box-shadow: 0 4px 0 #007052;
    }

    .toggle-button:active {
        transform: translateY(2px);
        box-shadow: 0 2px 0 #007052;
    } */
</style>
