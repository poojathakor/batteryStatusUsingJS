# batteryStatusUsingJS
code that will show your mobile is being charged or not, battery level and discharging time, simply using HTML and JS
```
window.onload = function () {
      function updateBatteryStatus(battery) {
        document.querySelector('#charging').textContent = battery.charging ? 'charging' : 'not charging';
        document.querySelector('#level').textContent = battery.level;
        document.querySelector('#dischargingTime').textContent = battery.dischargingTime / 60;
      }

      navigator.getBattery().then(function(battery) {
        // Update the battery status initially when the promise resolves ...
        updateBatteryStatus(battery);

        // .. and for any subsequent updates.
        battery.onchargingchange = function () {
          updateBatteryStatus(battery);
        };

        battery.onlevelchange = function () {
          updateBatteryStatus(battery);
        };

        battery.ondischargingtimechange = function () {
          updateBatteryStatus(battery);
        };
      });
    };
    
```
screenshot as attached

![alt text](https://github.com/poojathakor/batteryStatusUsingJS/blob/master/Picture1.png)
