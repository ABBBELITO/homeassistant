```YAML
# UnRAID Server Montitoring for Dwains-Theme
## Version 0.2 by noodlemctwoodle

# Please view the set up guide for this view on GitHub
## https://github.com/noodlemctwoodle/homeassistant/tree/master/user_content

# image: '/local/images/lovelace-themes/dwains-theme/software/unraid_logo.png'


- type: custom:dwains-flexbox-card
  padding: true
  items_classes: 'col-lg-6 col-md-6 col-sm-12 col-xs-12'
  cards:
    - type: horizontal-stack
      cards:

        - type: "custom:button-card"
          style: |
            ha-card {
              border-radius: 10px;
              box-shadow: 10px;
              background-position: center;
          entity: sensor.current_powered_on_plugs
          icon: mdi:power-socket-uk
#          name: Containers
          show_state: true
          show_name: true
          show_label: true
          show_icon: true
          styles:
            card:
              - background-size: contain
              - background-repeat: no-repeat
              - background-position: center
            icon:
              - width: 27%
              - margin-top: 1%


        - type: "custom:button-card"
          style: |
            ha-card {
              border-radius: 10px;
              box-shadow: 10px;
          entity: sensor.current_powered_on_devices
          icon: mdi:devices
          show_state: true
          show_name: true
          show_label: true
          show_icon: true
          styles:
            card:
              - background-size: contain
              - background-repeat: no-repeat
              - background-position: center
            icon:
              - width: 27%
              - margin-top: 1%

    - type: vertical-stack
      cards:
        - type: horizontal-stack
          cards:

        # Energy Pricing Input
            - type: entities
              style: |
                ha-card {
                  border-radius: 10px }};
                  box-shadow: 10px;
                  font-weight: bold;
                  opacity: 0.8;
                }
              head:
                type: section
                label: Power Rate Costs (Pence)
              entities:
              - entity: input_number.daily_service_charge
                icon: mdi:cash
              - entity: input_number.electricity_rate
                icon: mdi:cash


- type: custom:dwains-flexbox-card
  padding: true
  items_classes: 'col-lg-12 col-md-12 col-sm-12 col-xs-12'
  cards:
    - type: horizontal-stack
      cards:

        # Living Room TV
            - type: "custom:button-card"
              style: |
                ha-card {
                  background: url('/local/images/lovelace-themes/dwains-theme/hardware/smart-plug.png');
                  border-radius: 10px;
                  box-shadow: 10px;
              entity: switch.living_room_tv_smart_plug_relay
              name: Living Room TV
              icon: mdi:power-socket-uk
              show_state: false
              show_name: true
              show_label: true
              show_icon: false
              styles:
                card:
                  - background-size: contain
                  - background-repeat: no-repeat
                  - background-position: center
                name:
                  - align-self: bottom

              state:
                - value: 'off'
                  styles:
                    card:
                      - filter: grayscale(100%)
              custom_fields:
                switch: >
                  [[[
                    return `<ha-icon
                      style="width: 36px; height: 63px;">
                      </ha-icon>`
                  ]]]
              double_tap_action:
                action: call-service
                service: switch.toggle
                service_data:
                  entity_id: switch.living_room_tv_smart_plug_relay

        # Living Room AV Receiver
            - type: "custom:button-card"
              style: |
                ha-card {
                  background: url('/local/images/lovelace-themes/dwains-theme/hardware/smart-plug.png');
                  border-radius: 10px;
                  box-shadow: 10px;
              entity: switch.living_room_av_receiver_smart_plug_relay
              show_state: false
              show_name: false
              show_label: false
              show_icon: false
              styles:
                card:
                  - background-size: contain
                  - background-repeat: no-repeat
                  - background-position: center
                state:
                  - justify-self: left
              state:
                - value: 'off'
                  styles:
                    card:
                      - filter: grayscale(100%)
              custom_fields:
                switch: >
                  [[[
                    return `<ha-icon
                      style="width: 36px; height: 63px;">
                      </ha-icon>`
                  ]]]
              double_tap_action:
                action: call-service
                service: switch.toggle
                service_data:
                  entity_id: switch.living_room_av_receiver_smart_plug_relay

        # Living Room Sub
            - type: "custom:button-card"
              style: |
                ha-card {
                  background: url('/local/images/lovelace-themes/dwains-theme/hardware/smart-plug.png');
                  border-radius: 10px;
                  box-shadow: 10px;
              entity: switch.living_room_subwoofer_smart_socket
              show_state: false
              show_name: false
              show_label: false
              show_icon: false
              styles:
                card:
                  - background-size: contain
                  - background-repeat: no-repeat
                  - background-position: center
              state:
                - value: 'off'
                  styles:
                    card:
                      - filter: grayscale(100%)
              custom_fields:
                switch: >
                  [[[
                    return `<ha-icon
                      style="width: 36px; height: 63px;">
                      </ha-icon>`
                  ]]]
              double_tap_action:
                action: call-service
                service: switch.toggle
                service_data:
                  entity_id: switch.living_room_subwoofer_smart_socket

    - type: vertical-stack
      cards:
        - type: horizontal-stack
          cards:

        # Bedroom TV Smart Plug
            - type: "custom:button-card"
              style: |
                ha-card {
                  background: url('/local/images/lovelace-themes/dwains-theme/hardware/smart-plug.png');
                  border-radius: 10px;
                  box-shadow: 10px;
              entity: switch.bedroom_tv_smart_plug_relay
              icon: mdi:power-socket-uk
              show_state: false
              show_name: false
              show_label: false
              show_icon: false
              styles:
                card:
                  - background-size: contain
                  - background-repeat: no-repeat
                  - background-position: center
              state:
                - value: 'off'
                  styles:
                    card:
                      - filter: grayscale(100%)
              custom_fields:
                switch: >
                  [[[
                    return `<ha-icon
                      style="width: 36px; height: 63px;">
                      </ha-icon>`
                  ]]]
              double_tap_action:
                action: call-service
                service: switch.toggle
                service_data:
                  entity_id: switch.bedroom_tv_smart_plug_relay

        # Office Computer
            - type: "custom:button-card"
              style: |
                ha-card {
                  background: url('/local/images/lovelace-themes/dwains-theme/hardware/smart-plug.png');
                  border-radius: 10px;
                  box-shadow: 10px;
              entity: switch.office_computer_smart_plug_relay
              icon: mdi:power-socket-uk
              show_state: false
              show_name: false
              show_label: false
              show_icon: false
              styles:
                card:
                  - background-size: contain
                  - background-repeat: no-repeat
                  - background-position: center
              state:
                - value: 'off'
                  styles:
                    card:
                      - filter: grayscale(100%)
              custom_fields:
                switch: >
                  [[[
                    return `<ha-icon
                      style="width: 36px; height: 63px;">
                      </ha-icon>`
                  ]]]
              double_tap_action:
                action: call-service
                service: switch.toggle
                service_data:
                  entity_id: switch.office_computer_smart_plug_relay

        # Cabinet Smart Plug
            - type: "custom:button-card"
              style: |
                ha-card {
                  background: url('/local/images/lovelace-themes/dwains-theme/hardware/smart-plug.png');
                  border-radius: 10px;
                  box-shadow: 10px;
              entity: switch.cabinet_smart_plug_switch
              show_state: false
              show_name: false
              show_label: false
              show_icon: false
              styles:
                card:
                  - background-size: contain
                  - background-repeat: no-repeat
                  - background-position: center
              state:
                - value: 'off'
                  styles:
                    card:
                      - filter: grayscale(100%)
              custom_fields:
                switch: >
                  [[[
                    return `<ha-icon
                      style="width: 36px; height: 63px;">
                      </ha-icon>`
                  ]]]
              double_tap_action:
                action: call-service
                service: switch.toggle
                service_data:
                  entity_id: switch.cabinet_smart_plug_switch


- type: custom:dwains-flexbox-card
  padding: true
  items_classes: 'col-lg-6 col-md-6 col-sm-12 col-xs-12'
  cards:
    - type: horizontal-stack
      cards:

    # Now Energy Cost
        - type: 'custom:flex-horseshoe-card'
          style: |
            ha-card {
              border-radius: 10px;
              box-shadow: 10px;
            }
          entities:
            - entity: sensor.power_total_usage
              decimals: 0
              name: 'Current Power Use'
              unit: 'W'
              tap_action:
                action: none
            - entity: sensor.now_energy_cost
              attribute: Cost
              decimals: 2
#              unit: '£'
              icon: mdi:currency-gbp
              tap_action:
                action: none
          show:
            horseshoe_style: 'lineargradient'
          layout:
            hlines:
              # A horizontal line. Not connected to an entity
              - id: 0
                xpos: 50
                ypos: 55
                length: 40
                styles:
                  - stroke: var(--primary-text-color);
                  - stroke-width: 5;
                  - stroke-linecap: round;
                  - opacity: 0.7;
            states:
              # States 0 refers to the first entity in the list, ie index 0
              - id: 0
                entity_index: 0
                xpos: 50
                ypos: 45
                styles:
                  - font-size: 3em;
              # States 1 refers to the second entity in the list, ie index 1
              - id: 1
                entity_index: 1
                xpos: 40
                ypos: 69
                styles:
                  - text-anchor: start;
                  - font-size: 1.5em;
            icons:
              # Icons 0 refers to the second entity in the list, ie index 1
              - id: 1
                entity_index: 1
                xpos: 35
                ypos: 65
                size: 10
                styles:
                  - color: white;
                icon_size: 1.3
            names:
              # Names 0 refers to the first entity in the list, ie index 0
              - id: 0
                entity_index: 0
                xpos: 50
                ypos: 90
                styles:
                  - font-size: 1em;
          # Scale set to -10 to +40 degrees celcius
          horseshoe_scale:
            min: 20
            max: 600
          # color stop list with 10 colors defined in the theme. With the `lineargradient` fill style, only the
          # first (16:) and last (25:) colors are used. The thresholds are ignored with this setting.
          color_stops:
            16: '#26c941'
            17: '#6ac926'
            18: '#85c926'
            19: '#9ec926'
            20: '#b9c926'
            21: '#c9be26'
            22: '#c9a626'
            23: '#c99026'
            24: '#c96f26' 
            25: '#c92626' 

    # Daily Energy Cost
        - type: 'custom:flex-horseshoe-card'
          style: |
            ha-card {
              border-radius: 10px;
              box-shadow: 10px;
              background-position: center;
            }
          entities:
            - entity: sensor.energy_total_usage
              decimals: 1
              name: 'Usage Today'
              unit: 'KwH'
              tap_action:
                action: none
            - entity: sensor.daily_energy_cost
              attribute: Cost
              decimals: 2
              icon: mdi:currency-gbp
              tap_action:
                action: none
          show:
            horseshoe_style: 'lineargradient'
          layout:
            hlines:
              # A horizontal line. Not connected to an entity
              - id: 0
                xpos: 50
                ypos: 55
                length: 40
                styles:
                  - stroke: var(--primary-text-color);
                  - stroke-width: 5;
                  - stroke-linecap: round;
                  - opacity: 0.7;
            states:
              # States 0 refers to the first entity in the list, ie index 0
              - id: 0
                entity_index: 0
                xpos: 50
                ypos: 45
                styles:
                  - font-size: 3em;
              # States 1 refers to the second entity in the list, ie index 1
              - id: 1
                entity_index: 1
                xpos: 40
                ypos: 69
                styles:
                  - text-anchor: start;
                  - font-size: 1.5em;
            icons:
              # Icons 0 refers to the second entity in the list, ie index 1
              - id: 1
                entity_index: 1
                xpos: 35
                ypos: 65
                size: 10
                styles:
                  - color: white;
                icon_size: 1.3
            names:
              # Names 0 refers to the first entity in the list, ie index 0
              - id: 0
                entity_index: 0
                xpos: 50
                ypos: 90
                styles:
                  - font-size: 1em;
          # Scale set to -10 to +40 degrees celcius
          horseshoe_scale:
            min: 0
            max: 10
          # color stop list with 10 colors defined in the theme. With the `lineargradient` fill style, only the
          # first (16:) and last (25:) colors are used. The thresholds are ignored with this setting.
          color_stops:
            16: '#26c941'
            17: '#6ac926'
            18: '#85c926'
            19: '#9ec926'
            20: '#b9c926'
            21: '#c9be26'
            22: '#c9a626'
            23: '#c99026'
            24: '#c96f26' 
            25: '#c92626' 

    - type: vertical-stack
      cards:
        - type: horizontal-stack
          cards: 

        # Daily Energy Cost
            - type: 'custom:flex-horseshoe-card'
              style: |
                ha-card {
                  border-radius: 10px;
                  box-shadow: 10px;
                  background-position: center;
                }
              entities:
                - entity: sensor.daily_energy_kwh
                  decimals: 1
                  name: 'Daily Cost'
                  unit: 'KwH'
                  tap_action:
                    action: none
                - entity: sensor.daily_energy_cost
                  attribute: Cost
                  decimals: 2
                  icon: mdi:currency-gbp
                  tap_action:
                    action: none
              show:
                horseshoe_style: 'lineargradient'
              layout:
                hlines:
                  # A horizontal line. Not connected to an entity
                  - id: 0
                    xpos: 50
                    ypos: 55
                    length: 40
                    styles:
                      - stroke: var(--primary-text-color);
                      - stroke-width: 5;
                      - stroke-linecap: round;
                      - opacity: 0.7;
                states:
                  # States 0 refers to the first entity in the list, ie index 0
                  - id: 0
                    entity_index: 0
                    xpos: 50
                    ypos: 45
                    styles:
                      - font-size: 3em;
                  # States 1 refers to the second entity in the list, ie index 1
                  - id: 1
                    entity_index: 1
                    xpos: 40
                    ypos: 69
                    styles:
                      - text-anchor: start;
                      - font-size: 1.5em;
                icons:
                  # Icons 0 refers to the second entity in the list, ie index 1
                  - id: 1
                    entity_index: 1
                    xpos: 35
                    ypos: 65
                    size: 10
                    styles:
                      - color: white;
                    icon_size: 1.3
                names:
                  # Names 0 refers to the first entity in the list, ie index 0
                  - id: 0
                    entity_index: 0
                    xpos: 50
                    ypos: 90
                    styles:
                      - font-size: 1em;
              # Scale set to -10 to +40 degrees celcius
              horseshoe_scale:
                min: 0
                max: 10
              # color stop list with 10 colors defined in the theme. With the `lineargradient` fill style, only the
              # first (16:) and last (25:) colors are used. The thresholds are ignored with this setting.
              color_stops:
                16: '#26c941'
                17: '#6ac926'
                18: '#85c926'
                19: '#9ec926'
                20: '#b9c926'
                21: '#c9be26'
                22: '#c9a626'
                23: '#c99026'
                24: '#c96f26' 
                25: '#c92626' 


        # Monthly Energy Cost
            - type: 'custom:flex-horseshoe-card'
              style: |
                ha-card {
                  border-radius: 10px;
                  box-shadow: 10px;
                  background-position: center;
                }
              entities:
                - entity: sensor.monthly_energy_kwh
                  decimals: 0
                  name: 'Monthly Cost'
                  unit: 'KwH'
                  tap_action:
                    action: none
                - entity: sensor.monthly_energy_cost
                  attribute: Cost
                  decimals: 2
                  icon: mdi:currency-gbp
                  tap_action:
                    action: none
              show:
                horseshoe_style: 'lineargradient'
              layout:
                hlines:
                  # A horizontal line. Not connected to an entity
                  - id: 0
                    xpos: 50
                    ypos: 55
                    length: 40
                    styles:
                      - stroke: var(--primary-text-color);
                      - stroke-width: 5;
                      - stroke-linecap: round;
                      - opacity: 0.7;
                states:
                  # States 0 refers to the first entity in the list, ie index 0
                  - id: 0
                    entity_index: 0
                    xpos: 50
                    ypos: 45
                    styles:
                      - font-size: 3em;
                  # States 1 refers to the second entity in the list, ie index 1
                  - id: 1
                    entity_index: 1
                    xpos: 40
                    ypos: 69
                    styles:
                      - text-anchor: start;
                      - font-size: 1.5em;
                icons:
                  # Icons 0 refers to the second entity in the list, ie index 1
                  - id: 1
                    entity_index: 1
                    xpos: 35
                    ypos: 65
                    size: 10
                    styles:
                      - color: white;
                    icon_size: 1.3
                names:
                  # Names 0 refers to the first entity in the list, ie index 0
                  - id: 0
                    entity_index: 0
                    xpos: 50
                    ypos: 90
                    styles:
                      - font-size: 1em;
              # Scale set to -10 to +40 degrees celcius
              horseshoe_scale:
                min: 0
                max: 40
              # color stop list with 10 colors defined in the theme. With the `lineargradient` fill style, only the
              # first (16:) and last (25:) colors are used. The thresholds are ignored with this setting.
              color_stops:
                16: '#26c941'
                17: '#6ac926'
                18: '#85c926'
                19: '#9ec926'
                20: '#b9c926'
                21: '#c9be26'
                22: '#c9a626'
                23: '#c99026'
                24: '#c96f26' 
                25: '#c92626' 


- type: vertical-stack
  cards:
    - type: custom:dwains-flexbox-card
      padding: true
      items_classes: 'col-lg-6 col-md-6 col-sm-12 col-xs-12'
      cards:
        - type: vertical-stack
          cards:
            - type: horizontal-stack
              cards:
            # UnRAID Array Status
                - type: custom:bar-card
                  item_classes: 'col-lg-3 col-md-3'
                  style: |-
                    :host {
                      --ha-card-background: var(--dwains-theme-primary);
                      --ha-card-border-radius: 10px;
                      --ha-card-box-shadow: 10px;
                      --ha-card-opacity: 0.8;
                      card-backgroundbar: 0px;
                    }
                    bar-card-title {
                      margin-bottom: 0px;
                    }
                    bar-card-divider {
                      display: none;
                    }
                    bar-card-value {
                      margin-right: auto;
                      margin-left: 20px;
                      margin-bottom: auto;
                      margin-top: 0px;
                    }
                    bar-card-title {
                      margin-bottom: 3px;
                      margin-top: 3px;
                    }
                  entities: 
                    - entity: sensor.unraid_array_status_numerical
                      name: Array Status
                      icon: mdi:code-array
                    - entity: sensor.unraid_array_protection_numerical
                      name: Array Protection
                      icon: mdi:harddisk-plus
                  show_icon: true
                  positions:
                    name: inside
                    value: 'off'
                    icon: inside
                  severity:
                    - color: Green
                      from: 0
                      to: 1
                    - color: Red
                      from: 1
                      to: 0
                  direction: right
                  stack: horizontal
                  columns: 1
                  max: 1
                  min: 0
                  tap_action: none

        - type: horizontal-stack
          cards:

        # UnRAID Array Total Space
            - type: custom:bar-card
              item_classes: 'col-lg-3 col-md-3'
              style: |
                :host {
                  --ha-card-background: var(--dwains-theme-primary);
                  --ha-card-border-radius: 10px;
                  --ha-card-box-shadow: 10px;
                  --ha-card-font-weight: bold;
                  --ha-card-opacity: 0.8;
                }
                ha-card {
                  font-size: 10px;                 
                }
                bar-card-value {
                  font-size: 10px;
                }
              entity: sensor.unraid_array_space
              icon: mdi:database-settings
              show_icon: true
              positions:
                name: inside
                value: inside
                icon: inside
              severity:
                - color: '#3cff00'
                  from: 0
                  to: 30
                - color: '#ccff00'
                  from: 31
                  to: 40
                - color: '#d9d21c'
                  from: 41
                  to: 50
                - color: '#f7da00'
                  from: 51
                  to: 60
                - color: '#edac09'
                  from: 61
                  to: 70
                - color: '#ffa408'
                  from: 71
                  to: 80
                - color: '#ff5e08'
                  from: 81
                  to: 90
                - color: '#ed0909'
                  from: 91
                  to: 100
              direction: right
              columns: 1
              max: 100
              min: 0
              tap_action: none

        # Disk Space Used Card

        - type: horizontal-stack
          cards:
            - type: custom:swipe-card
              parameters:
                spaceBetween: 8
                touchEventsTarget: 'container'
                pagination:
                  type: 'bullets'
                  dynamicBullets: true

              cards:

                - type: vertical-stack
                  cards:
                    - type: horizontal-stack
                      cards: 

                    # Disk 1 Used %
                        - type: custom:bar-card
                          style: |
                            :host {
                              --ha-card-background: var(--paper-card-background-color);
                              --ha-card-border-radius: 10px;
                              --ha-card-box-shadow: 10px;
                              --ha-card-font-weight: bold;
                              --ha-card-opacity: 0.8;
                            }
                            ha-card {
                              font-size: 10px;                 
                            }
                            bar-card-value {
                              font-size: 10px;
                              margin: 100px;
                            }
                            bar-card-name {
                              text-align: center;
                            }
                            ha-icon {
                              text-align: center;
                            }
                          entities: 
                            - entity: sensor.bedroom_tv_smart_plug_wattage
                              name: Bedroom TV
                              icon: mdi:power-socket-uk
                            - entity: sensor.living_room_av_receiver_smart_plug_wattage
                              name: Living Room AV
                              icon: mdi:power-socket-uk
                            - entity: sensor.office_computer_smart_plug_wattage
                              name: Office Computer
                              icon: mdi:power-socket-uk
                            - entity: sensor.living_room_tv_smart_plug_wattage
                              name: Living Room TV
                              icon: mdi:power-socket-uk
                            - entity: sensor.cabinet_smart_plug_power
                              name: Server Cabinet
                              icon: mdi:power-socket-uk
                          show_icon: false
                          height: 180px
                          stack: horizontal
                          positions:
                            name: inside
                            value: inside
                            icon: inside
                          severity:
                            - color: '#3cff00'
                              from: 0
                              to: 30
                            - color: '#ccff00'
                              from: 30
                              to: 50
                            - color: '#f1f505'
                              from: 50
                              to: 100
                            - color: '#f7da00'
                              from: 100
                              to: 150
                            - color: '#edac09'
                              from: 150
                              to: 200
                            - color: '#ffa408'
                              from: 200
                              to: 250
                            - color: '#ff5e08'
                              from: 250
                              to: 350
                            - color: '#ed0909'
                              from: 350
                              to: 450
                          direction: up
                          columns: 1
                          max: 450
                          min: 0
                          tap_action: none

                - type: vertical-stack
                  cards:
                    - type: horizontal-stack
                      cards: 

                    # 6 TB Disks Free Space
                        - type: custom:bar-card
                          style: |
                            :host {
                              --ha-card-background: var(--paper-card-background-color);
                              --ha-card-border-radius: 10px;
                              --ha-card-box-shadow: 10px;
                              --ha-card-font-weight: bold;
                              --ha-card-opacity: 0.8;
                            }
                            ha-card {
                              font-size: 10px;                 
                            }
                            bar-card-value {
                              font-size: 10px;
                              margin: 100px;
                            }
                            bar-card-name {
                              text-align: center;
                            }
                            ha-icon {
                              text-align: center;
                            }
                          entities: 
                            - entity: sensor.bedroom_tv_smart_plug_total_daily_energy
                              name: Bedroom TV
                              icon: mdi:power-socket-uk
                            - entity: sensor.living_room_av_receiver_smart_plug_total_daily_energy
                              name: Living Room AV
                              icon: mdi:power-socket-uk
                            - entity: sensor.office_computer_smart_plug_total_daily_energy
                              name: Office Computer
                              icon: mdi:power-socket-uk
                            - entity: sensor.living_room_tv_smart_plug_total_daily_energy
                              name: Living Room TV
                              icon: mdi:power-socket-uk
                            - entity: sensor.cabinet_smart_plug_energy
                              name: Server Cabinet
                              icon: mdi:power-socket-uk
                          show_icon: true
                          height: 180px
                          stack: horizontal
                          positions:
                            name: inside
                            value: inside
                            icon: inside
                          severity:
                            - color: '#fa0505'
                              from: 0
                              to: 700
                            - color: '#de4314'
                              from: 700
                              to: 800
                            - color: '#d1861d'
                              from: 800
                              to: 900
                            - color: '#d4c11c'
                              from: 900
                              to: 1000
                            - color: '#64c91c'
                              from: 1001
                              to: 5560
                          direction: up
                          columns: 1
                          max: 450
                          min: 0
                          tap_action: none


        - type: vertical-stack
          cards:

            - type: horizontal-stack
              cards:
                - type: custom:swipe-card
                  parameters:
                    spaceBetween: 8
                    touchEventsTarget: 'container'
                    pagination:
                      type: 'bullets'
                      dynamicBullets: true

                  cards:
                    - type: horizontal-stack
                      cards: 

                  # LAN Download
                        - type: custom:mini-graph-card
                          item_classes: 'col-lg-6 col-md-6'
                          style: |
                            ha-card {
                              background: var(--paper-card-background-color);
                              border-radius: 10px;
                              box-shadow: 10px;
                              font-weight: bold;
                              opacity: 0.8;
                            }
                          entities:
                            - entity: sensor.bedroom_tv_smart_plug_wattage
                              name: Bedroom TV
                              color: '#f205b3' # Pink
                            - entity: sensor.living_room_av_receiver_smart_plug_wattage
                              name: Living Room AV
                              color: '#f20505' # Red
                            - entity: sensor.office_computer_smart_plug_wattage
                              name: Office Computer
                              color: '#05f248' # Green
                            - entity: sensor.living_room_tv_smart_plug_wattage
                              name: Living Room TV
                              color: '#e9fa02' # Yellow
                            - entity: sensor.cabinet_smart_plug_power
                              name: Server Cabinet
                              color: '#0293fa' # Sky Blue
                          name: Smart Plug Watts 24 Hours
                          icon: mdi:power-socket-uk
                          hours_to_show: 24
                          points_per_hour: 60
                          update_interval: 120
                          aggregate_func: avg
                          line_width: 1
                          smoothing: false
                          font_size: 65
                          font_size_header: 9
                          show:
                            graph: line
                            average: true
                            extrema: true
                          tap_action: none

                    - type: vertical-stack
                      cards:

                  # LAN Upload
                        - type: custom:mini-graph-card
                          item_classes: 'col-lg-6 col-md-6'
                          style: |
                            ha-card {
                              background: var(--paper-card-background-color);
                              border-radius: 10px;
                              box-shadow: 10px;
                              font-weight: bold;
                              opacity: 0.8;
                            }
                          entities:
                            - entity: sensor.bedroom_tv_smart_plug_total_daily_energy
                              name: Bedroom TV
                              color: '#f205b3' # Pink
                            - entity: sensor.living_room_av_receiver_smart_plug_total_daily_energy
                              name: Living Room AV
                              color: '#f20505' # Red
                            - entity: sensor.office_computer_smart_plug_total_daily_energy
                              name: Office Computer
                              color: '#05f248' # Green
                            - entity: sensor.living_room_tv_smart_plug_total_daily_energy
                              name: Living Room TV
                              color: '#e9fa02' # Yellow
                            - entity: sensor.cabinet_smart_plug_energy
                              name: Server Cabinet
                              color: '#0293fa' # Sky Blue
                          name: Smart Plug KwH 24 Hours
                          icon: mdi:power-socket-uk
                          hours_to_show: 24
                          points_per_hour: 60
                          update_interval: 120
                          aggregate_func: avg
                          line_width: 1
                          smoothing: false
                          font_size: 65
                          font_size_header: 9
                          show:
                            graph: line
                            average: true
                            extrema: true
                          tap_action: none

- type: vertical-stack
  cards:
    - type: custom:dwains-flexbox-card
      padding: true
      items_classes: 'col-lg-6 col-md-6 col-sm-12 col-xs-12'
      cards:




        - type: horizontal-stack
          cards:
            - type: custom:swipe-card
              parameters:
                spaceBetween: 8
                touchEventsTarget: 'container'
                pagination:
                  type: 'bullets'
                  dynamicBullets: true

              cards:
                - type: horizontal-stack
                  cards:

              # Cache Disk Usage
                    - type: custom:mini-graph-card
                      item_classes: 'col-lg-6 col-md-6'
                      style: |
                        ha-card {
                          background: var(--paper-card-background-color);
                          border-radius: 10px;
                          box-shadow: 10px;
                          font-weight: bold;
                          opacity: 0.8;
                        }
                      entities:
                        - entity: sensor.glances_unraid_mnt_cache_used
                          name: Cache
                          color: '#f205b3' # Pink
                      name: Cache Used Space
                      icon: mdi:harddisk-plus
                      hours_to_show: 168
                      points_per_hour: 1
                      update_interval: 120
                      aggregate_func: avg
                      line_width: 2
                      height: 120
                      smoothing: false
                      font_size: 65
                      font_size_header: 9
                      show:
                        graph: line
                        average: true
                        extrema: true
                      tap_action: none

                - type: vertical-stack
                  cards:

              # Backups Disk Usage
                    - type: custom:mini-graph-card
                      item_classes: 'col-lg-6 col-md-6'
                      style: |
                        ha-card {
                          background: var(--paper-card-background-color);
                          border-radius: 10px;
                          box-shadow: 10px;
                          font-weight: bold;
                          opacity: 0.8;
                        }
                      entities:
                        - entity: sensor.glances_unraid_mnt_disks_backups_used
                          name: Backups Disk
                          color: '#0293fa' # Sky Blue
                      name: Backups Used Spcace
                      icon: mdi:upload-network
                      hours_to_show: 168
                      points_per_hour: 1
                      update_interval: 120
                      aggregate_func: avg
                      line_width: 2
                      height: 120
                      smoothing: true
                      font_size: 65
                      font_size_header: 9
                      show:
                        graph: line
                        average: true
                        extrema: true
                      tap_action: none
```