<template>
  <v-content>
    <h2>Convert From</h2>
    <v-expansion-panel inset>
      <v-expansion-panel-content
        v-for="types in conversionTypes"
        :key="types.title"
        >
        <div slot="header">{{types.title}}</div>
        <v-card>
          <v-expansion-panel inset>
            <v-expansion-panel-content
              v-for="unitType in types.unitType"
              :key="unitType.typeTitle"
              >
              <div slot="header">{{unitType.typeTitle}}</div>
              <v-card>
                <v-expansion-panel inset>
                  <v-expansion-panel-content
                    v-for="unit in unitType.units"
                    :key="unit.title"
                    >
                    <div slot="header">{{unit.title}}</div>
                    <v-card>
                      <v-card-text>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                      </v-card-text>
                    </v-card>
                  </v-expansion-panel-content>
                </v-expansion-panel>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-card>
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-content>
</template>

<script>
export default {
  data () {
    return {
      conversionTypes: {
        length: {
          title: 'Length',
          unitType: {
            metric: {
              typeTitle: 'Metric',
              units: {
                mm: {
                  title: 'Millimeter'
                },
                cm: {
                  title: 'Centimeter'
                },
                meter: {
                  title: 'Meter'
                }
              }
            },
            imerial: {
              typeTitle: 'Imperial',
              units: {
                inch: {
                  title: 'Inch'
                },
                foot: {
                  title: 'Foot'
                },
                yard: {
                  title: 'Yard'
                },
                mile: {
                  title: 'Mile'
                }
              }
            }
          }
        },
        volume: {
          title: 'Volume',
          unitType: {
            metric: {
              typeTitle: 'Metric',
              units: {
                ml: {
                  title: 'Milliliter'
                },
                cl: {
                  title: 'Centiliter'
                },
                l: {
                  title: 'Liter'
                }
              }
            },
            imerial: {
              typeTitle: 'Imperial',
              units: {
                teaspoon: {
                  title: 'Teaspoon'
                },
                tablespoon: {
                  title: 'Tablespoon'
                },
                ounce: {
                  title: 'Fluid Ounce'
                },
                cup: {
                  title: 'Cup'
                },
                pint: {
                  title: 'Pint'
                },
                quart: {
                  title: 'Quart'
                },
                gallon: {
                  title: 'Gallon'
                }
              }
            }
          }
        },
        mass: {
          title: 'Mass',
          unitType: {
            metric: {
              typeTitle: 'Metric',
              units: {
                mg: {
                  title: 'Milligram'
                },
                g: {
                  title: 'Gram'
                },
                kg: {
                  title: 'Kilogram'
                }
              }
            },
            imerial: {
              typeTitle: 'Imperial',
              units: {
                ounce: {
                  title: 'Ounce'
                },
                lb: {
                  title: 'Pound'
                },
                ton: {
                  title: 'Ton'
                }
              }
            }
          }
        },
        energy: {
          title: 'Energy',
          unitType: {
            metric: {
              typeTitle: 'Metric',
              units: {
                joule: {
                  title: 'Joule'
                },
                kiloJoule: {
                  title: 'Kilojoule'
                },
                therm: {
                  title: 'Therms'
                }
              }
            },
            imerial: {
              typeTitle: 'Imperial',
              units: {
                calorie: {
                  title: 'Calorie'
                },
                kcal: {
                  title: 'KiloCalorie'
                },
                hp: {
                  title: 'Horsepower'
                },
                ftlb: {
                  title: 'Foot-Pound'
                },
                btu: {
                  title: 'BTU'
                },
                watt: {
                  title: 'Watts'
                }
              }
            }
          }
        }
      }
    }
  }
}
</script>

<style>

</style>
