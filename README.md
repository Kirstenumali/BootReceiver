# BootReceiver in Java

1. Add a User Permission
``` bash
    <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />
``` 
2. Add a class name BootReceiver
``` bash
package com.ubtrobot.callingsystemservices;

import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
import android.util.Log;

public class BootReceiver extends BroadcastReceiver {

    @Override
    public void onReceive(Context context, Intent intent) {
        if (Intent.ACTION_BOOT_COMPLETED.equals(intent.getAction())) {
            Intent i = new Intent(context, <ActivityName>.class);
            i.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
            context.startActivity(i);
            Log.d("BootReceiver", "App launched at startup");
        }
    }
}
```

3. Test it
