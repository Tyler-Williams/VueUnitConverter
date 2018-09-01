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
                        <v-layout row>
                          <v-flex xs9>
                            <v-text-field
                            v-bind="{label: 'Measurement'}"
                            v-model="unitQuantity"></v-text-field>
                          </v-flex>
                          <v-flex xs3>
                            <v-btn v-on:click="convert(types.title, unit.title, unitQuantity)">Convert</v-btn>
                          </v-flex>
                        </v-layout>
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
    <v-layout row>
      <v-flex xs3></v-flex>
      <v-flex xs6>
        <v-card>
          <v-card-title>
            <h4>{{converted.title}}</h4>
          </v-card-title>
          <v-divider></v-divider>
          <v-container >
            <v-layout
            align-center
            justify-space-between
            row
            pt-3
            v-for="item in converted.items"
            :key="item.title">
              <div>{{item.title}}</div>
              <div>{{item.value}}{{item.units}}</div>
            </v-layout>
          </v-container>
        </v-card>
      </v-flex>
    </v-layout>
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
                },
                nm: {
                  title: 'Newton-Meters'
                }
              }
            },
            imerial: {
              typeTitle: 'Imperial',
              units: {
                calorie: {
                  title: 'Calorie'
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
      },
      converted: {
        title: 'TEST',
        items: [
          {
          title: 'Kilometers',
          value: '100',
          units: 'KM'
          },
          {
          title: 'Feet',
          value: '300',
          units: 'FT'
          }
        ]
      },
      unitQuantity: null,
      showLength: false,
      showVolume: false,
      showEnergy: false,
      showMass: false
    }
  },
  methods: {
    convert (type, unit, quantity) {
      console.log(type, unit, quantity)
    }
  }
}
</script>

<style>

</style>
