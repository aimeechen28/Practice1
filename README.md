# Practice1
Question 1 Part A: 

public boolean simulate(){ 

    int num = 0; 

    int currentSum = 0; 

    while(currentSum<goalDistance && currentSum>=0 && num<maxHops){ 

        currentSum += hopDistance(); 

        num++; 

    } 

    if(currentSum >= goalDistance) return true; 

    return false; 

} 

 

Question 1 Part B: 

public double runSimulations(int num){ 

    int trueTime = 0; 

    for(int i = 0; i<num;i++){ 

    if(simulate() == true) trueTime++; 

} 

    return (double)(trueTime/num); 

} 

 

 

 

Question 2 Part A: 

    public int nextTankToFill(int threshold){ 

       int mini = tanks.get(0).getFuelLevel(); 

       int index = 0; 

        for(int i = 0; i<tanks.size();i++){ 

          if(mini > tanks.get(i).getFuelLevel()){ 

            mini = tanks.get(i).getFuelLevel(); 

            index = i; 

        } 

        } 

        if(tanks.get(index).getFuelLevel() <= threshold)return index; 

        else return filler.getCurrentIndex(); 

         

    } 

 

    Question 2 Part B: 

    public void moveToLocation(int locIndex){ 

        while(locIndex >= 0 && locIndex <tanks.size()){ 

            if(locIndex > filler.getCurrentIndex()){ 

                filler.moveForward(locIndex-filler.getCurrentIndex()); 

            }else if(locIndex < filler.getCurrentIndex()){ 

                filler.changeDirection(); 

                filler.moveForward(filler.getCurrentIndex()-locIndex); 

            }else{ 

                locIndex = filler.getCurrentIndex(); 

            } 

           

        } 

         

    } 
