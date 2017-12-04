# Java-Timer-Time-Counter
We are going to use Timer class of swing (javax.swing.Timer).

Create a Timer:

private long startTime = -1;
private long initialTime = 0;
SimpleDateFormat df = new SimpleDateFormat("HH:mm:ss");


Timer  timer = new Timer(10, new ActionListener() {
                @Override
                public void actionPerformed(ActionEvent e) {
                    if (startTime < 0) {
                        startTime = System.currentTimeMillis();
                        System.out.println("Start: "+startTime);
                    }
                    long now = System.currentTimeMillis();
                    System.out.println("Now: "+now);
                    long clockTime = now - startTime;
                    System.out.println("clockTime: "+clockTime);
                    df.setTimeZone(TimeZone.getTimeZone("GMT"));
                    jLabel1.setText(df.format(clockTime));
                }
            });



Start the timer:

timer.start();

Stop the timer:

timer.stop();



