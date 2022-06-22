<template>

  <ul class="filter-bar">
    <div class="filter-wrap">
      <div class="filter-input">
        <img class="sort-icon" src="https://universe.leagueoflegends.com/esimages/content_type_icon_champion__3nwJQ.png" alt="Champion Icon">
        <div>
          <input class="search" type="text" placeholder="Trova un campione" />
        </div>
      </div>
      <li class="filter-button">
        <div class="button-content">
          <img src="../assets/imgs/sortingicon.png" alt="">
          <h5>
            <span class="sorting-label">Ordina per</span>
            <span class="secondary-text"> : 
              <span class="sorting-alphabetical">A-Z</span>
            </span>
          </h5>
        </div>
        <div class="small-filter-parent">
          <div class="small-filter invisible visible">
            <ul>
              <li>
                <span class="sorting-alphabetical">A-Z</span>
              </li>
              <li>
                <span class="sorting-newest">Novità</span>
              </li>
              <li>
                <span class="sorting-faction">Regione</span>
              </li>
            </ul>
          </div>
        </div>
      </li>
    </div>
  </ul>

</template>

<script>
export default {
    name: 'Filters',
}
</script>

<style lang="scss" scoped>
.filter-bar {
  position: relative;
  background-color: #121212;
  left: 0;
  margin: 0;
  max-width: 100vw;
  opacity: 1;
  right: 0;
  box-sizing: inherit;
  z-index: 10000;
}
.filter-wrap {
  align-items: center;
  background-color: #121212;
  box-shadow: 0 16px 16px -16px rgb(0 0 0 / 70%);
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  max-width: 1280px;
  padding: 0 30px;
  width: 100%;
  z-index: 200;
}
.filter-input {
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
}
.sort-icon {
  max-height: 32px;
  padding-right: 20px;
}
.search {
  font-family: BeaufortforLOL-Bold, sans-serif;
  font-weight: 700;
  font-size: 14px;
  color: rgb(147, 115, 65);
  letter-spacing: 4px;
  text-transform: uppercase;
  background-color: rgba(0,0,0,0);
  border: 0;
  min-width: 650px;
  padding: 35px 12px;
  &:focus {
    outline: none;
  }
}
.filter-button {
  border-width: 0 1px!important;
  max-width: 50%;
  width: 30%;
  align-items: center;
  cursor: pointer;
  display: flex;
  height: 90px;
  justify-content: center;
  position: relative;
  z-index: 100;
}
.button-content {
  background-image: radial-gradient(ellipse at 50% 12%,rgba(0,0,0,0),rgba(0,0,0,0) 40%);
  align-items: center;
  background-color: #121212;
  display: flex;
  height: 100%;
  justify-content: flex-start;
  width: 100%;
  z-index: 100;
  &:hover {
    background-image: radial-gradient(ellipse at 50% 12%,#1b2528,#121212 40%);
  }
}
.filter-button img {
  max-height: 20px;
  padding: 2px 30px 0 15px;
}
.sorting-label {
  font-family: Beaufort for LOL,Arial,sans-serif;
  font-weight: 700;
  font-size: 14px;
  color: #c4b998;
  letter-spacing: 4px;
  overflow: hidden;
  text-align: left;
  text-transform: uppercase;
}
.secondary-text {
  font-family: Beaufort for LOL,Arial,sans-serif;
  font-weight: 700;
  font-size: 14px;
  color: #937341;
  letter-spacing: 4px;
  overflow: hidden;
  text-align: left;
  text-transform: uppercase;
}
.small-filter-parent {
  z-index: -1;
}
.small-filter {
  left: 0;
  width: 100%;
  position: absolute;
  top: 90px;
  transition: transform .5s ease;
  background-image: radial-gradient(circle at 50% 12%,#1b1b1b,#121212 40%);
  z-index: 99;
}
.invisible {
  transform: translateY(-325px);
  opacity: 0;
}
.small-filter .invisible {
  cursor: default;
  pointer-events: none;
}
.small-filter li {
  font-family: Beaufort for LOL,Arial,sans-serif;
  font-weight: 700;
  font-size: 12px;
  transition: .2s;
  color: #c4b998;
  letter-spacing: 2px;
  padding: 16px 32px 16px 67px;
  text-align: left;
  text-transform: uppercase;
}

.filter-wrapper {
  position: sticky;
  z-index: 5;
  animation: 1000ms cubic-bezier(0.215, 0.61, 0.355, 1) 500ms 1 normal both running;
  @media (min-width: 1001px) {
    top: 10px;
  }
}
nav {
  display: block;
  margin: 0px 2%;
}
.nav-inner {
  position: relative;
  display: block;
  margin: 0px auto;
  max-width: 1400px;
  box-sizing: border-box;
  background-color: #000913;
}
.nav-container {
    right: 2px;
    position: absolute;
    inset: 1px;
    pointer-events: none;
}
canvas {
  position: absolute;
  display: block;
  aspect-ratio: auto 2802 / 104;
}
.nav-content {
  box-sizing: border-box;
  height: 50px;
  position: relative;
  display: flex;
  -webkit-box-align: stretch;
  align-items: stretch;
}
.nav-side {
  min-width: 138px;
  position: relative;
  flex: 0 1 auto;
  display: flex;
  -webkit-box-align: center;
  align-items: center;
}
.dropdown {
  height: 100%;
  font-size: 10px;
  letter-spacing: 0.1em;
  font-weight: 600;
  text-transform: uppercase;
  position: relative;
  box-sizing: border-box;
}
.dropdown-control {
  cursor: pointer;
  height: 100%;
  min-height: 0px;
  padding: 0px 30px;
  border: 0px;
  box-shadow: none;
  background-color: transparent;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  display: flex;
  flex-wrap: wrap;
  outline: 0 !important;
  position: relative;
  transition: all 100ms;
  box-sizing: border-box;
  ::before {
    content: "";
    position: absolute;
    top: 10px;
    bottom: 10px;
    right: 0px;
    width: 1px;
    background-color: rgb(193, 193, 193);
    transition: top 250ms ease 0s, bottom 250ms ease 0s;
  }
}
.dropdown-value-container {
  padding: 0px;
  display: flex;
  flex: 0 0 auto;
  -webkit-box-align: center;
  flex-wrap: wrap;
  position: relative;
  overflow: hidden;
  box-sizing: border-box;
}
.svg-icon {
  position: absolute;
  left: 5px;
  top: 0px;
  transition: left 250ms ease 0s;
  width: 19px;
  height: 19px;
  overflow: hidden;
}
.st0 {
  fill: rgb(194, 144, 45);
}
.st1 {
  fill: none;
  stroke: rgb(194, 144, 45);
  stroke-width: 1.5;
  stroke-miterlimit: 10;
}
.dropdown-placeholder {
  position: static;
  top: auto;
  color: white;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
  margin: 0px;
  transform: none;
  transition: color 250ms ease 0s;
  box-sizing: border-box;
}
.nonloso {
  margin: 2px;
  padding-bottom: 2px;
  padding-top: 2px;
  visibility: visible;
  color: white;
  box-sizing: border-box;
}
.nav-side2 {
  min-width: 172px;
    position: relative;
  flex: 0 1 auto;
  display: flex;
  -webkit-box-align: center;
  align-items: center;
}
.role-container {
  flex: 1 0 auto;
}
.role-list {
  height: 100%;
  margin: 0px;
  padding: 0px;
  list-style: none;
  text-align: center;
}

ul {
  display: block;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  padding-inline-start: 40px;
}

.role-item {
  display: inline-block;
  font-size: 10px;
  height: 100%;
  text-align: -webkit-match-parent;
}
.role-button {
  position: relative;
  display: block;
  height: 100%;
  padding: 0px 10px;
  border: 0px;
  background-color: transparent;
  box-sizing: border-box;
  letter-spacing: 0.1em;
  font-weight: 600;
  text-transform: uppercase;
  transition: color 300ms ease 0s;
  color: white;
  &::after {
    content: "";
    position: absolute;
    left: 0px;
    bottom: 0px;
    width: 100%;
    height: 3px;
    background-color: rgb(194, 144, 45);
    transform: scale(0, 1);
    transition: transform 300ms ease 0s;
}
}
</style>