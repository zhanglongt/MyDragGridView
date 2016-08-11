
        //判断是否可以拖拽
        gv.setDragOutOfParent(true);
        gv.setDragChangeHandler(new IDragChangeHandler() {
            @Override
            public Object getItemDataByPos(int position) {
                Log.i("ii",position+"");
                return sim_adapter1.getItem(position);
            }

            @Override
            public void onDragPosChange(int oldPos, int newPos) {
                Log.i("ii",oldPos+":"+newPos);

                Object item = data_list1.remove(oldPos);
                data_list1.add(newPos, item);
                c.getResult().getSpec_tree().getColor().setGray(data_list1);
                sim_adapter1.notifyDataSetChanged();
            }
        });