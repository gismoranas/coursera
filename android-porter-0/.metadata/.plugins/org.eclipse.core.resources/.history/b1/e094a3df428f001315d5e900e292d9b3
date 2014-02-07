package course.labs.activitylab;

import android.app.Activity;
import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.view.View.OnClickListener;
import android.widget.Button;
import android.widget.TextView;

public class ActivityOne extends Activity {

	private static final String RESTART_KEY = "restart";
	private static final String RESUME_KEY = "resume";
	private static final String START_KEY = "start";
	private static final String CREATE_KEY = "create";

	// String for LogCat documentation
	private final static String TAG = "Lab-ActivityOne";
	
	// Lifecycle counters
	// Create counter variables for onCreate(), onRestart(), onStart() and
	// onResume(), called mCreate, etc.
	// You will need to increment these variables' values when their
	// corresponding lifecycle methods get called
  private int onCreateCounter = 0;
  private int onRestartCounter = 0;
  private int onStartCounter = 0;
  private int onResumeCounter = 0;

	// Create variables for each of the TextViews, called
  // mTvCreate, etc. 
  private TextView onCreateTextView; 
  private TextView onRestartTextView; 
  private TextView onStartTextView; 
  private TextView onResumeTextView; 

	
	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_one);
		
		// TODO: Assign the appropriate TextViews to the TextView variables
		// Hint: Access the TextView by calling Activity's findViewById()
		// textView1 = (TextView) findViewById(R.id.textView1);
    onCreateTextView = (TextView) findViewById(R.id.CREATE_KEY);
    onRestartTextView = (TextView) findViewById(R.id.RESTART_KEY);
    onStartTextView = (TextView) findViewById(R.id.START_KEY);
    onResumeTextView = (TextView) findViewById(R.id.RESUME_KEY);

		Button launchActivityTwoButton = (Button) findViewById(R.id.bLaunchActivityTwo); 
		launchActivityTwoButton.setOnClickListener(new OnClickListener() {
			
			@Override
			public void onClick(View view) {
				// Launch Activity Two
				// Hint: use Context's startActivity() method

				// Create an intent stating which Activity you would like to start
        Intent intent = new Intent();
        intent.setComponent(new ComponentName("course.lab.activitylab", "course.lab.activitylab.ActivityTwo"));
				// Launch the Activity using the intent
			  view.getContext().startActivity(intent);
			
			}
		});
		
		// Check for previously saved state
		if (savedInstanceState != null) {

			// Restore value of counters from saved state
			// Only need 4 lines of code, one for every count variable
      onRestartCounter = savedInstanceState.getInt(RESTART_KEY);       			
      onResumeCounter = savedInstanceState.getInt(RESUME_KEY);       			
      onStartCounter = savedInstanceState.getInt(START_KEY);       			
      onCreateCounter = savedInstanceState.getInt(CREATE_KEY);       			
		
		}

		// Emit LogCat message
    Log.i(CREATE_KEY);

		// Update the appropriate count variable
    onCreateCounter++;
		
    // Update the user interface via the displayCounts() method
    displayCounts();

	}

	// Lifecycle callback overrides

	@Override
	public void onStart() {
		super.onStart();
		// Emit LogCat message
    Log.i(START_KEY);
		// Update the appropriate count variable
    onStartCounter++;
		// Update the user interface
    displayCounts();

	}

	@Override
	public void onResume() {
		super.onResume();
		// Emit LogCat message
    Log.i(RESUME_KEY);
		// Update the appropriate count variable
    onResumeCounter++;
		// Update the user interface
    displayCounts();

	}

	@Override
	public void onPause() {
		super.onPause();

		// Emit LogCat message
    Log.i("pause");

	}

	@Override
	public void onStop() {
		super.onStop();

		// Emit LogCat message
    Log.i("stop");

	}

	@Override
	public void onRestart() {
		super.onRestart();

		// Emit LogCat message
    Log.i(RESTART_KEY);
		// Update the appropriate count variable
    onRestartCounter++;
		// Update the user interface
    displayCounts();

	}

	@Override
	public void onDestroy() {
		super.onDestroy();

		// Emit LogCat message
    Log.i("destroy");

	}

	@Override
	public void onSaveInstanceState(Bundle savedInstanceState) {
		// Save state information with a collection of key-value pairs
		// 4 lines of code, one for every count variable
    savedInstanceState.putInt(START_KEY, onStartCounter);
    savedInstanceState.putInt(RESTART_KEY, onRestartCounter);
    savedInstanceState.putInt(RESUME_KEY, onResumeCounter);
    savedInstanceState.putInt(CREATE_KEY, onCreateCounter);

	}
	
	// Updates the displayed counters
	public void displayCounts() {

		onCreateTextView.setText("onCreate() calls: " + mCreate);
		onStartTextView.setText("onStart() calls: " + mStart);
		onResumeTextView.setText("onResume() calls: " + mResume);
		onRestartTextView.setText("onRestart() calls: " + mRestart);
	
	}
}
