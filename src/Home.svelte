

<h1 class="home--title text">Lifestyle</h1>
<h2 class="home--intro text">The latest and best lifestyle articles selected by our editorial office</h2>

<section class="home--section">
        <div class="article one">
            <h4 class="article--tag">food</h4>
            <h3 class="article--title">Wake Up and Smell the Coffee</h3>
            <button class="article--read-more">read more</button>
        </div>

        <div class="article two">
            <h4 class="article--tag">interior</h4>
            <h3 class="article--title">9 Air-Cleaning Plants Your Home Needs</h3>
            <button class="article--read-more">read more</button>
        </div>

        <div class="article three">
            <h4 class="article--tag">food</h4>
            <h3 class="article--title">One Month Sugar Detox</h3>
            <button class="article--read-more">read more</button>
        </div>

        <div class="article four">
            <h4 class="article--tag">architecture</h4>
            <h3 class="article--title">The Brand New NASA Office</h3>
            <button class="article--read-more">read more</button>
        </div>

        <div class="article five">
            <h4 class="article--tag">travel</h4>
            <h3 class="article--title">Experience the Saharan Sands</h3>
            <button class="article--read-more">read more</button>
        </div>

        <div class="article six">
            <h4 class="article--tag">photography</h4>
            <h3 class="article--title">Shooting Minimal Instagram Photos</h3>
            <button class="article--read-more">read more</button>
        </div>
</section>


<style>

    .text {
        font-family: "Calibri", sans-serif;
    }

    .home--title {
        font-size : 2.5rem;
        margin-left : 5rem;
    }

    .home--intro {
        font-size : 1rem;
        margin-left : 5rem;

    }

    .home--section {
        display : grid;
        grid-template-columns: repeat(4, 1fr);
        grid-gap : 0.75rem;
        margin : 5rem;
    }

    .article {
        border-radius: 0.5rem;
        box-shadow: 2px 2px 5px lightgray;
        padding : 1rem 0;
    }

    .one {
        grid-column: 1/3;
        grid-row: 1/2;
        background: linear-gradient(to right, #72aaa7, #d4e0e1);
    }

    .two{
        grid-column: 1/2;
        grid-row: 2/4;
        background: linear-gradient(#3BA8C7, #C8E0ED);
    }

    .three{
        grid-column: 2/3;
        grid-row: 2/4;
        background: linear-gradient(#FDA4A8, #F1DDDF);
    }

    .four{
        grid-column: 3/4;
        grid-row: 1/3;
        background: linear-gradient(#142331, #90bfff);
    }

    .five{
        grid-column: 4/5;
        grid-row: 1/3;
        background: linear-gradient(#D1A989, #EED6C3);
    }

    .six{
        grid-row : 3/4;
        grid-column: 3/5;
        background: linear-gradient(to right, #64BFFD, #E0F0FA);
    }

    .article--tag {
        color : white;
        text-transform: uppercase;
        font-size : 0.8rem;
        padding-left : 1rem;
    }

    .article--title {
        color : white;
        font-weight : bold;
        font-size : 1.5rem;
        padding-left : 1rem;

    }

    .article--read-more{
        border : none;
        border-radius: 0.3rem;
        color : inherit;
        box-shadow: 2px 2px 2px grey;
        margin : 1rem;
    }

    @media (max-width : 900px){
        .home--section {
            grid-template-columns: repeat(2, 1fr);
            margin : 2rem;
        }

        .four {
            grid-column : 1/2;
            grid-row: 4/6;
        }

        .five {
            grid-column : 2/3;
            grid-row: 4/6;
        }

        .six {
            grid-column : 1/3;
            grid-row: 6/7;
        }
    }

    @media (max-width : 480px){
        .home--section {
            margin : 1rem;
        }
    }
</style>

