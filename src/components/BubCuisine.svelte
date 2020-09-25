<script>
  let cuisine = undefined;

  const cuisines = [
    {
      img: "assets/indian-cuisine.jpg",
      title: "indian",
      description: `Indian cuisine consists of a variety of regional and traditional cuisines native to the Indian subcontinent. Given the diversity in soil, climate, culture, ethnic groups, and occupations, these cuisines vary substantially and use locally available spices, herbs, vegetables, and fruits. Indian food is also heavily influenced by religion, in particular Hinduism, cultural choices and traditions. Centuries of Islamic rule, particularly by the Mughals, also introduced dishes like samosa and pilaf.`,
    },
    {
      img: "assets/mexican-cuisine.jpg",
      title: "mexican",
      description: `Mexican cuisine began about nine thousand years ago, when agricultural communities such as the Maya formed, domesticating maize, creating the standard process of maize nixtamalization, and establishing their foodways (Maya cuisine). Successive waves of other Mesoamerican groups brought with them their own cooking methods. These included the Olmec, Teotihuacanos, Toltec, Huastec, Zapotec, Mixtec, Otomi, Purépecha, Totonac, Mazatec, Mazahua, and Nahua. With the Mexica formation of the multi-ethnic Triple Alliance (Aztec Empire), culinary foodways became infused (Aztec cuisine). The staples are native foods, such as corn (maize), beans, squash, amaranth, chia, avocados, tomatoes, tomatillos, cacao, vanilla, agave, turkey, spirulina, sweet potato, cactus, and chili pepper.`,
    },
    {
      img: "assets/dutch-cuisine.jpg",
      title: "dutch",
      description: `Dutch cuisine (Dutch: Nederlandse keuken) is formed from the cooking traditions and practices of the Netherlands. The country's cuisine is shaped by its location in the fertile North Sea river delta of the European Plain, giving rise to fishing, farming (for crops and domesticated animals), and trading over sea, its former colonial empire and the spice trade.

Traditionally, Dutch cuisine is simple and straightforward, with many vegetables and little meat: breakfast and lunch are typically bread with toppings like cheese, while dinner is meat and potatoes, supplemented with seasonal vegetables. The diet contains many dairy products and was relatively high in carbohydrates and fat, reflecting the dietary needs of the laborers whose culture molded the country. Without many refinements, it is best described as rustic, though many holidays are celebrated with special foods.`,
    },
    {
      img: "assets/american-cuisine.jpg",
      title: "american",
      description: `American cuisine reflects the history of the United States, blending the culinary contributions of various groups of people from around the world, including indigenous American Indians, African Americans, Asians, Europeans, Pacific Islanders, and Latin Americans. Though much of American cuisine is fusion cuisine reflecting global cuisine, many regional cuisines have deeply rooted ethnic heritages, including Cajun, Louisiana Creole, Native American, New Mexican, Pennsylvania Dutch, Soul food, and Tlingit. Early Native Americans utilized a number of cooking methods in early American cuisine that have been blended with early European cooking methods to form the basis of what is now American cuisine. The European settlement of the Americas introduced a number of ingredients, spices, herbs, and cooking styles to the continent. The various styles of cuisine continued expanding well into the 19th and 20th centuries, proportional to the influx of immigrants from many different nations; this influx nurtured a rich diversity in food preparation throughout the country.`,
    },
    {
      img: "assets/british-cuisine.jpg",
      title: "british",
      description: `British cuisine is the heritage of cooking traditions and practices associated with the United Kingdom. Although Britain has a rich indigenous culinary tradition, its colonial history has profoundly enriched its native cooking traditions. British cuisine absorbed the cultural influences of its post-colonial territories – in particular those of South Asia.


Fish and chips, a popular take-away food of the United Kingdom
In ancient times Celtic agriculture and animal breeding produced a wide variety of foodstuffs for the indigenous Celts and Britons. Anglo-Saxon England developed meat and savoury herb stewing techniques before the practice became common in Europe. The Norman conquest introduced exotic spices into England in the Middle Ages. The British Empire facilitated a knowledge of Indian cuisine with its "strong, penetrating spices and herbs". Food rationing policies put into place by the British government during the wartime periods of the 20th century are widely considered today to be responsible for British cuisine's poor international reputation.

Well-known traditional British dishes include full breakfast, fish and chips, the Christmas dinner, the Sunday roast, steak and kidney pie, shepherd's pie, and bangers and mash. People in Britain, however, eat a wide variety of foods based on the cuisines of Europe, India, and other parts of the world. British cuisine has many regional varieties within the broader categories of English, Scottish and Welsh cuisine and Northern Irish cuisine. Each has developed its own regional or local dishes, many of which are geographically indicated foods such as Cornish pasties, the Yorkshire pudding, Cumberland Sausage, Arbroath Smokie, and Welsh cakes.`,
    },
    {
      img: "assets/japanese-cuisine.jpg",
      title: "japanese",
      description: `Japanese cuisine encompasses the regional and traditional foods of Japan, which have developed through centuries of political, economic, and social changes.

The traditional cuisine of Japan, washoku (和食), lit. "Japanese eating" (or kappō (ja:割烹)), is based on rice with miso soup and other dishes; there is an emphasis on seasonal ingredients. Side dishes often consist of fish, pickled vegetables, and vegetables cooked in broth. Seafood is common, often grilled, but also served raw as sashimi or in sushi. Seafood and vegetables are also deep-fried in a light batter, as tempura. Apart from rice, staples include noodles, such as soba and udon. Japan also has many simmered dishes such as fish products in broth called oden, or beef in sukiyaki and nikujaga.`,
    },
    {
      img: "assets/australian-cuisine.jpg",
      title: "australian",
      description: `Australian cuisine refers to the food and cooking practices of Australia and its inhabitants. As a modern nation of large-scale immigration, Australia has a unique blend of culinary contributions and adaptations from various cultures around the world, including British, European, Asian and Middle Eastern.

Indigenous Australians have occupied Australia for some 65,000 years, during which they developed a unique hunter-gatherer diet, known as bush tucker, drawn from regional Australian flora and fauna. Australia became a collection of British colonies from 1788 to 1900, during which time culinary tastes were strongly influenced by British and Irish migrants, with agricultural products such as beef cattle, sheep and wheat becoming staples in the local diet. The Australian gold rushes introduced more varied immigrants and cuisines, mainly Chinese, whilst post-war immigration programs led to a large-scale diversification of local food, particularly under the influence of migrants from the Mediterranean, East Asia and South Asia.

Australian cuisine in the 21st century reflects the influence of globalisation, with many fast-food restaurants and international trends becoming influential. Organic and biodynamic foods have also become widely available alongside a revival of interest in bush tucker. Australia has become known for the high quality of its exports, with major agricultural industries including cattle, sheep, poultry, milk, vegetables, fruit, nuts, wheat, barley and canola. The country is also well regarded for its locally-made wine, beer and soft drinks.

While fast food chains are abundant, Australia's metropolitan areas have fine dining establishments that offer both local and international foods. Restaurants whose product includes contemporary adaptations, interpretations or fusions of exotic influences are frequently termed Modern Australian.`,
    },
  ];

  function getRandomInt(max) {
    return Math.floor(Math.random() * Math.floor(max));
  }

  function cuisineSelector() {
    cuisine = cuisines[getRandomInt(cuisines.length)];
  }
</script>

<style type="text/postcss">
  .button {
    @apply bg-orange-600 text-white font-bold py-2 px-4 border border-gray-400 rounded;
  }

  .button:hover {
    @apply bg-orange-700;
  }
</style>

<div class="h-screen bg-gray-200">
  <div class="flex items-center justify-center h-56">
    <button class="button" on:click={() => cuisineSelector()}>
      Select a cuisine!
    </button>
  </div>

  {#if cuisine}
    <div class="flex items-center justify-center bg-gray-200">
      <div class="w-full lg:w-8/12 lg:flex">
        <div
          class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t
            lg:rounded-t-none lg:rounded-l text-center overflow-hidden"
          style="background-image: url('{cuisine.img}')"
          title="Woman holding a mug" />
        <div
          class="border-r border-b border-l border-gray-400 lg:border-l-0
            lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none
            lg:rounded-r p-4 flex flex-col justify-between leading-normal">
          <div class="mb-8">
            <div class="text-gray-900 font-bold text-xl mb-2">
              Selected cuisine is {cuisine.title}!
            </div>
            <p class="text-gray-700 text-base">{cuisine.description}</p>
          </div>
        </div>
      </div>
    </div>
  {/if}
</div>
