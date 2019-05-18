# HistoryofWestrenPhilosophy
при изменение БД изменить version
https://ru.wikipedia.org/wiki/История_философии
https://qa-help.ru/questions/kak-peredat-znachenie-int-iz-odnoj-aktivnosti-v-druguyu
http://developer.alexanderklimov.ru/android/listactivity.php#longclick
 
 public void searchItem(String textToSearch) {
        for (String item : items) {
            String textToSearch1 = textToSearch.toLowerCase();

            if (!item.toLowerCase().contains(textToSearch1)) {
                listItems.remove(item);
            }
        }
        adapter.notifyDataSetChanged();
    }
    Cursor cursor = mDb.query("PT",
            new String[]{"Name"}, null, null,
            null, null, null);
    public void initList() {
        String a[]=new String[10];
        int i=0;
        cursor.moveToFirst();
        while (!cursor.isAfterLast()) {
           a[i]= cursor.getString(1)+"";
           cursor.moveToNext();
                   i++;
        }cursor.close();
        items = a;
            listItems = new ArrayList<>(Arrays.asList(items));
            adapter = new ArrayAdapter<String>(this, R.layout.list_item, R.id.txtitem, listItems);
            listView.setAdapter(adapter);

    }
