var pCard1=0;
var pCard1Old="";
var pCard1Alt="";

var pCard2=0;
var pCard2Old="";
var pCard2Alt="";

var dCard=0;
var dCardOld="";
var dCardAlt="";

function cardval() {
  var x = event.target;
  if (pCard1Old) pCard1Old.style.outline = "none";
  x.style.outline = "thick solid #FAD315";
  pCard1Old = event.target;
  pCard1Alt = event.srcElement.alt;
	pCard1 = Number(x.title);
  if (pCard1 > 0 && pCard2 > 0 && dCard > 0) TBJWIZ();
}

function cardval2() {
  var x = event.target;
  if (pCard2Old) pCard2Old.style.outline = "none";
  x.style.outline = "thick solid #FAD315";
  pCard2 = Number(x.title);
  pCard2Old = event.target;
  pCard2Alt = event.srcElement.alt;
  if (pCard1 > 0 && pCard2 > 0 && dCard > 0) TBJWIZ();
}

function cardval3() {
  var x = event.target;
  if (dCardOld) dCardOld.style.outline = "none";
  x.style.outline = "thick solid #FAD315";
  dCard = Number(x.title);
  dCardOld = event.target;
  dCardAlt = event.srcElement.alt;
  if (pCard1 > 0 && pCard2 > 0 && dCard > 0) TBJWIZ();
}

function TBJWIZ() {
  var str = [
    "111111111111000001111110001111110001111112002",
    "111113310000000001111100001111100002213222202",
    "111133310000000001111330001111330002213222202",
    "111133300000000001133330001133330002213222202",
    "111133300000000003333330003333330002223222202",
    "111133300000000003333330003333330002223222202",
    "111113311111000001111100001111100002213122002",
    "111113311111000001111100001111100001113112202",
    "111113311111000001111110001111110001113112202",
    "111111311111000001111110001111110001111112002",
    "111111111111000001111110001111110001111112002"
  ];
  var res = "";
  var pAction = 0;
  var pCard = pCard1 + pCard2;
  document.getElementById('total').innerHTML = pCard;

  var action = ["Stand", "Hit", "Split", "Double Down"];

  if (pCard1Alt === pCard2Alt) {
    document.getElementById('strategy').innerHTML = "Splitting Pairs";
    pAction = Number(str[dCard - 1].substr(pCard1 + 33, 1));
    //document.getElementById('pActiondebug').innerHTML = pAction;
    res = action[pAction];
  }

  if (pCard2 === 11 && pcard1 !== 11) {
    document.getElementById('strategy').innerHTML = "Softhand Strategy";
    pAction = Number(str[dCard - 1].substr(pCard1 + 24, 1));
    //document.getElementById('pActiondebug').innerHTML = pAction;
    res = action[pAction];
  }

  if (pCard1 === 11 && pCard2 !== 11) {
    document.getElementById('strategy').innerHTML = "Softhand Strategy";
    pAction = Number(str[dCard - 1].substr(pCard2 + 15, 1));
    //document.getElementById('pActiondebug').innerHTML = pAction;
    res = action[pAction];
  }

  if ((pCard1Alt !== pCard2Alt) && res === "") {
    document.getElementById('strategy').innerHTML = "Basic Strategy";
    pAction = Number(str[dCard - 1].substr(pCard - 5, 1));
    //document.getElementById('pActiondebug').innerHTML = pAction;
    res = action[pAction];
  }

  if (res === "") {
    res = "Error";
  }
	document.getElementById('act').innerHTML = res;
}
