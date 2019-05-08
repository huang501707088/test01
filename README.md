    private void minMax( List<AccessBean> accessBeanList){


        int listSize = accessBeanList.size();
        LogUtils.d("accessBeanList size --" + listSize);

        String[] infor = new String[listSize];
        String tempString;
        long[] positionArrays = new long[listSize];
        int[] index = new int[listSize];
        for(int i=0;i<listSize;i++){
           infor[i] = accessBeanList.get(i).access_time;
            tempString =  infor[i].replace("-","").replace(" ","").replace(":","");
            LogUtils.d("infor["+i+"] = "+tempString);
            positionArrays[i] = Long.parseLong(tempString);
        }

        //冒泡排序实现
        for(int i=0;i<positionArrays.length-1;i++){
            for(int j=0;j<positionArrays.length-i-1;j++){
                if(positionArrays[j]>positionArrays[j+1]){
                    long temp = positionArrays[j];
                    positionArrays[j] = positionArrays[j+1];
                    positionArrays[j+1] = temp;
                }
            }
        }
        for(int i=0;i<listSize;i++){
            LogUtils.d("positionArrays["+i+"] = " +positionArrays[i]);
        }
        String min = ""+positionArrays[0];
        String max = ""+positionArrays[listSize-1];
    }
