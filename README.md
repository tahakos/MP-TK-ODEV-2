# MP-TK-ODEV-2
MP TK ODEV 2
s 212 odev;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;
import java.util.ArrayList;
public class MainActivity extends AppCompatActivity {
    Button buttonEkle;
    EditText editTextAd;
    ListView listViewAdlar;
    ArrayList<String> isimlerinListesi = new ArrayList<>();
    ArrayAdapter<String> adapter;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, isimlerinListesi);
        buttonEkle = findViewById(R.id.buttonEkle);
        editTextAd = findViewById(R.id.editTextAd);
        listViewAdlar = findViewById(R.id.listViewAdlar);
        listViewAdlar.setAdapter(adapter);
        buttonEkle.setOnClickListener(view -> {
            String ad = editTextAd.getText().toString();
            isimlerinListesi.add(ad);
            adapter.notifyDataSetChanged();
            editTextAd.getText().clear();
        });
