<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

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
                [2019, 6.1]
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
                [2019, 3]
            ],
            color: "#ff99fc",
        },
    ];

    let chart;
    let thirdSeriesVisible = false;

    let options = {
        chart: {
            type: "spline",
            backgroundColor: "#e3ff00",
            borderColor: "#007052",
            borderWidth: 5,
            borderRadius: 20,
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
            </div>
            <button on:click={toggleThirdSeries} class="toggle-button">
                {thirdSeriesVisible ? "Remove Group 3" : "Add Group 3"}
            </button>
            <div>
                <p>
                    You can use Svelte to add and remove data from a Highcharts
                    chart.
                </p>
                <p>
                    When you click the button above, a third group is toggled in
                    the chart. Check out the source code to see how it's done.
                </p>
                <p>
                    <strong
                        >🤔 How might you use other HTML elements, like
                        checkboxes or radio buttons, in a similar way to filter
                        data?</strong
                    >
                </p>
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                You might notice that this basic template doesn't have certain
                features that are common in scrollytelling.
            </ArticleText>

            <ArticleText>
                For example, you might want a component that doesn't feature a
                sticky component at all. Or a component that is solely a sticky
                component.
            </ArticleText>

            <ArticleText>
                You might also want to add more interactivity or gamify parts of
                your scrollytelling piece.
            </ArticleText>

            <ArticleText>
                <strong>
                    It's up to you to research how to create the effects and
                    functionality that you envision!
                </strong>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .chart {
        width: 90%;
        margin: 0px auto;
    }

    .toggle-button {
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
    }
</style>
