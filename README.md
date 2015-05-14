# CustomToast
Simple Custom toast 

**Custom Toast**  
This code can be used to create custom toast.

![Screen](https://github.com/ashokslsk/CustomToast/blob/master/SimpleCustomToast/screens/1.png)
![Screen](https://github.com/ashokslsk/CustomToast/blob/master/SimpleCustomToast/screens/2.png)

**CODES**


```sh

// ClassName.java
import android.app.Activity;
import android.os.Bundle;
import android.view.Gravity;
import android.view.LayoutInflater;
import android.view.View;
import android.view.View.OnClickListener;
import android.view.ViewGroup;
import android.widget.Button;
import android.widget.ImageView;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends Activity {

	private Button button;
	
	public void onCreate(Bundle savedInstanceState) {

		super.onCreate(savedInstanceState);
		setContentView(R.layout.main);

		button = (Button) findViewById(R.id.buttonToast);

		button.setOnClickListener(new OnClickListener() {

			@Override
			public void onClick(View arg0) {

				// get your custom_toast.xml ayout
				LayoutInflater inflater = getLayoutInflater();

				View layout = inflater.inflate(R.layout.custom_toast,
						(ViewGroup) findViewById(R.id.custom_toast_layout_id));

				// set a dummy image
				ImageView image = (ImageView) layout.findViewById(R.id.image);
				image.setImageResource(R.drawable.ic_launcher);

				// set a message
				TextView text = (TextView) layout.findViewById(R.id.text);
				text.setText("Button is clicked!");

				// Toast...
				Toast toast = new Toast(getApplicationContext());
				toast.setGravity(Gravity.CENTER_VERTICAL, 0, 0);
				toast.setDuration(Toast.LENGTH_LONG);
				toast.setView(layout);
				toast.show();

			}
		});

	}
}


// Custom_toast.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/custom_toast_layout_id"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:background="#FFF"
    android:orientation="horizontal"
    android:padding="5dp" >

    <ImageView
        android:id="@+id/image"
        android:layout_width="wrap_content"
        android:layout_height="fill_parent"
        android:layout_marginRight="5dp" />

    <TextView
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="fill_parent"
        android:textColor="#000" />

</LinearLayout>

//Main.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >
        
    <Button
        android:id="@+id/buttonToast"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Show Toast" />
    
</LinearLayout>

```

- Execute it as simple as it is 

* [For more codes, funs and for queries be in touch with @ashokslsk ](https://github.com/ashokslsk)

