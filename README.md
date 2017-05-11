public class MainActivity extends AppCompatActivity {
    int quantity = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

    }

    public void increment(View view){
        quantity = quantity+1;
        display(quantity);
    }
    public void decrement(View view){
        quantity = quantity-1;
        if (quantity<0){
            Toast.makeText(this, "Error", Toast.LENGTH_SHORT).show();
        }
        else {
            display(quantity);
        }
    }
    @RequiresApi(api = Build.VERSION_CODES.N)
    public void submitOrder(View view){
        int numberOfcoffee = quantity;
        display(numberOfcoffee);
        displayPrice(numberOfcoffee*5);
        String Message = "Thank You ";
        displayMessage(Message);

    }


    public void display(int number){

        TextView quantity = (TextView) findViewById(R.id.quantity);
        quantity.setText(""+number);
    }
    @RequiresApi(api = Build.VERSION_CODES.N)
    private void displayPrice(int number) {
        TextView price = (TextView) findViewById(R.id.price);
        price.setText(NumberFormat.getCurrencyInstance().format(number));
    }
    private void displayMessage(String message) {
        TextView price = (TextView) findViewById(R.id.message);
        price.setText(message);

    }
}
