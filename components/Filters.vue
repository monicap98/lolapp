<template>

    <div class="filter-wrapper">
        <nav>
          <div class="nav-inner">
            <div class="nav-container">
              <canvas class="style__Canvas-sc-1c9bc3r-1 hsvRhV" width="2766" height="104" style="width: 1383.4px; height: 52px; left: -2px; top: -2px;"></canvas>
            </div>
              <div class="nav-content">
                <div class="nav-side">
                  <div class="dropdown">
                    <div class="dropdown-control">
                      <div class="dropdown-value-container">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 15.69 15.69" class="svg-icon">
                          <path class="st0" d="M6.46 1.5c2.74 0 4.96 2.23 4.96 4.96s-2.23 4.96-4.96 4.96S1.5 9.2 1.5 6.46 3.73 1.5 6.46 1.5m0-1.5C2.89 0 0 2.89 0 6.46s2.89 6.46 6.46 6.46 6.46-2.89 6.46-6.46C12.93 2.89 10.03 0 6.46 0z"></path>
                          <path class="st1" d="M10.25 10.26l4.89 4.89"></path>
                        </svg>
                        <div class="dropdown-placeholder">Cerca</div>
                        <div class="nonloso">
                          <div class="dropdown-input">
                            <input
                              type="text" autocapitalize="none" autocomplete="off" autocorrect="off" id="react-select-2-input" spellcheck="false" tabindex="0" value="" aria-autocomplete="list" style="box-sizing: content-box; width: 2px; background: 0px center; border: 0px; font-size: inherit; opacity: 1; outline: 0px; padding: 0px; color: inherit;">
                            <div
                              style="position: absolute; top: 0px; left: 0px; visibility: hidden; height: 0px; overflow: scroll; white-space: pre; font-size: 10px; font-family: 'Spiegel'; font-weight: 600; font-style: normal; letter-spacing: 1px; text-transform: uppercase;">
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="role-container">
                  <ul class="role-list">
                    <li class="role-item"><button class="role-button">Tutto</button></li>
                    <li class="role-item"><button class="role-button">Assassini</button></li>
                    <li class="role-item"><button class="role-button">Combattenti</button></li>
                    <li class="role-item"><button class="role-button">Maghi</button></li>
                    <li class="role-item"><button class="role-button">Tiratori</button></li>
                    <li class="role-item"><button class="role-button">Supporti</button></li>
                    <li class="role-item"><button class="role-button">Tank</button></li>
                  </ul>
                </div>
                <div class="nav-side2">Tutte le difficoltà</div>
              </div>
          </div>
        </nav>
    </div>

</template>

<script>
export default {
    name: 'Filters',
}
</script>

<style lang="scss" scoped>
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