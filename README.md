Download Link: https://assignmentchef.com/product/solved-comp1406-assignment-3
<br>
In this assignment, you will simulate a police database that keeps track of a driver’s history with respect to the number of times they were pulled over and ticketed for  an infraction (i.e., a driving violation).   The database will make use of <strong>Arrays</strong> so as  to allow many drivers, vehicles and infractions to be stored together in lists.  We  will design a very small system and test it with only a few cars and owners.




<ul>

 <li>The <strong>Driver, Vehicle </strong>&amp;<strong> Infraction </strong>Classes</li>

</ul>

Define a class called <strong>Driver </strong>that defines the following attributes:

<strong><u>license</u></strong> – a String representing a driver’s license ID (e.g. “L0678-67825-83940”); <strong><u>name</u></strong> – a String representing the name of the driver

<strong><u>street</u></strong> – a String representing the street name and number for this driver (e.g., “12 Elm St.”);  <strong><u>city</u></strong> – a String representing the city in which this driver lives <strong><u>province</u></strong> – a String representing the province in which this driver lives

Write the following in the <strong>Driver</strong> class:

<ul>

 <li>a proper constructor that takes 5 parameters for all 5 attributes in the order shown above a proper zero-parameter constructor that calls the first constructor with appropriate values</li>

 <li>a <strong>toString()</strong> method that returns a string in the following format:</li>

</ul>

<strong>“#L0678-67825-83940 John Doe living at 12 Elm St., Ottawa, ON” </strong>

Define a class called <strong>Vehicle </strong>that defines the following attributes:

<strong><u>make</u></strong> – a string representing the company that made the vehicle (e.g., “Pontiac”, “Honda”, etc..) <strong><u>model</u></strong> – a string representing the model of the vehicle (e.g., “Grand Prix”, “Civic”, etc..) <strong><u>year</u></strong> – an <strong>int</strong> representing the year of the vehicle (e.g., 2004 etc..) <strong><u>color</u></strong> – a string representing the color of the vehicle (e.g., “red”, “blue” etc..)

<strong><u>plate</u></strong> – a string representing the license plate of the vehicle (e.g., “X5T6Y8”, “2FAST”, etc..) <strong><u>owner</u></strong> – a <strong>Driver</strong> object representing the owner of the vehicle (e.g., John Doe from part 1) <strong><u>reportedStolen</u></strong> – a <strong>boolean</strong> indicating whether or not the vehicle has been reported as stolen

Write the following in the <strong>Vehicle</strong> class:

<ul>

 <li>a proper constructor that takes 5 parameters for the first 5 attributes in the order shown above (assume new vehicles are not stolen and there is no owner yet).</li>

 <li>a proper zero-parameter constructor that calls the first constructor with appropriate values</li>

 <li>a <strong>toString()</strong> method that returns a string in the following format:</li>

</ul>

<strong>“A blue 1998 Honda Civic with plate X5T6Y8”</strong>




Define a class called <strong>Infraction </strong>(i.e., an <em>infraction </em>is a violation) that defines the following attributes:

<strong><u>amount</u></strong> – a <strong>float</strong> indicating how much the fine was for this infraction  <strong><u>description</u></strong> – a String describing the infraction (e.g., “Not stopping for red light”) <strong><u>dateIssued</u></strong> – a <strong>Date</strong> representing the date and time at which the infraction occurred.

You must import<strong> java.util.Date</strong> in order for your code to compile.

<strong><u>outstanding</u></strong> – a <strong>boolean</strong> indicating whether or not the infraction was paid yet <strong><u>driver </u></strong> – a <strong>Driver</strong> object representing the driver that received the infraction




Write the following in the <strong>Infraction</strong> class:

<ul>

 <li>a proper constructor that takes 3 parameters for the first 3 attributes in the order shown above</li>

 <li>a proper constructor that takes zero-parameters and calls the above constructor</li>

 <li>a <strong>toString()</strong> method that returns a string with the format below (use the <strong>format()</strong> method to format the amount to 2 decimal places and to display the date/time. The portion of the format string for displaying the date is “%tc”.  If the infraction has been paid, it should state [PAID IN FULL] as shown, otherwise it should state [OUTSTANDING]):</li>

</ul>




<strong>“$100.00 Infraction on Sun Jul 14 07:08:00 EDT 2002 [PAID IN FULL]” </strong>




<ul>

 <li>a method called <strong>pay()</strong> which pays the infraction (hint…use <strong>outstanding </strong>attribute)</li>

</ul>




____________________________________________________________________________________________




<ul>

 <li>The <strong>PoliceDatabase </strong>Class</li>

</ul>

Define a class called <strong>PoliceDatabase</strong> with the following instance variables:

<strong><u>vehicles</u></strong> – an <strong>array</strong> storing all vehicles in the database

<strong><u>numVehicles</u></strong> – an <strong>int</strong> that keeps track of how many vehicles there are in the database




<strong><u>drivers</u></strong> – an <strong>array</strong> storing all drivers (i.e., people who drive vehicles) in the database  <strong><u>numDrivers</u></strong> – an <strong>int</strong> that keeps track of how many drivers there are in the database




<strong><u>infractions</u></strong> – an <strong>array</strong> storing all infractions that have ever been given to drivers

<strong><u>numInfractions</u></strong> – an <strong>int</strong> that keeps track of how many infractions there are in the database




Write the following in the <strong>PoliceDatabase</strong> class:

<ul>

 <li>three static <u>constants</u> to represent the database size limits so that at most <strong>2000 drivers</strong>, at most <strong>1000 vehicles</strong> and at most <strong>800 infractions</strong> are allowed to be added to the database. Make sure that the rest of your code adheres to these exact limits.</li>

 <li>a zero-parameter constructor that initializes all the arrays properly</li>

 <li>a <strong>registerDriver(Driver aDriver) </strong>method which takes <strong>aDriver</strong> object as a parameter and then registers (i.e., remembers for later) the driver in the database … assuming that the database is not full, otherwise the driver is not to be registered.</li>

 <li>a <strong>registerVehicle(Vehicle aVehicle, String license) </strong>method which takes <strong>aVehicle</strong> object as a parameter and the <strong>license</strong> ID of a driver who owns the vehicle (i.e., this is not the license plate of the vehicle)  and then registers the vehicle in the database, making sure to also store the vehicle’s <u>owner</u> properly … assuming that the database is not full, otherwise the vehicle is not to be registered.</li>

 <li>a <strong>unregisterVehicle(String plate) </strong>method which takes a vehicle’s <strong>plate</strong> number as a parameter and then removes the vehicle from the database without altering the order of the vehicles currently in the database and without leaving any gaps in the array. If the <strong>plate</strong> is not in the database, then nothing is to be done.</li>

 <li>a <strong>reportStolen(String plate)</strong> method which records that the vehicle with the given <strong>plate</strong> number has been stolen. If the <strong>plate</strong> is not in the database, then nothing is to be done.</li>

 <li>a <strong>changeOwner(String plate, String license)</strong> method which updates the database by changing the owner information for the vehicle with the given <strong>plate</strong> to the driver with the given <strong>license</strong> ID (i.e., this second parameter is not the license plate of the vehicle). If the <strong>plate</strong> or <strong>license</strong> is not in the database, then nothing is to be done.</li>

</ul>

____________________________________________________________________________________________

<h1> (3) Some Testing to Make Sure That It All Works So Far</h1>




Copy (cut and paste from the file, do not re-type) the <strong>example()</strong> method on the next page into your <strong>PoliceDatabase</strong> class.   It is a method that builds and returns a <strong>PoliceDatabase</strong> object with some drivers and vehicles already registered.  Re-compile to make sure that you have no errors.




<strong>public static  </strong>PoliceDatabase example() { <em>// Register all drivers and their vehicles </em>

<em>    </em>PoliceDatabase pdb = <strong>new </strong>PoliceDatabase();

pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L1567-34323-84980”</strong>, <strong>“Matt Adore”</strong>,

<strong>“1323 Kenaston St.”</strong>, <strong>“Gloucester”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L0453-65433-87655”</strong>, <strong>“Bob B. Pins”</strong>,

<strong>“32 Rideau Rd.”</strong>, <strong>“Greely”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L2333-45645-54354”</strong>, <strong>“Stan Dupp”</strong>,

<strong>“1355 Louis Lane”</strong>, <strong>“Gloucester”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L1234-35489-99837”</strong>, <strong>“Ben Dover”</strong>,

<strong>“2348 Walkley Rd.”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L8192-87498-27387”</strong>, <strong>“Patty O’Lantern”</strong>,

<strong>“2338 Carling Ave.”</strong>, <strong>“Nepean”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L2325-45789-35647”</strong>, <strong>“Ilene Dover”</strong>,

<strong>“287 Bank St.”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L1213-92475-03984”</strong>, <strong>“Patty O’Furniture”</strong>,

<strong>“200 St. Laurant Blvd.”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L1948-87265-34782”</strong>, <strong>“Jen Tull”</strong>,

<strong>“1654 Stonehenge Cres.”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L0678-67825-83940”</strong>, <strong>“Jim Class”</strong>,

<strong>“98 Oak Blvd.”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L0122-43643-73286”</strong>, <strong>“Mark Mywords”</strong>,

<strong>“3 Third St.”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L6987-34532-43334”</strong>, <strong>“Bob Upandown”</strong>,

<strong>“434 Gatineau Way”</strong>, <strong>“Hull”</strong>, <strong>“QC”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L3345-32390-23789”</strong>, <strong>“Carrie Meehome”</strong>,

<strong>“123 Thurston Drive”</strong>, <strong>“Kanata”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L3545-45396-88983”</strong>, <strong>“Sam Pull”</strong>,

<strong>“22 Colonel By Drive”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L1144-26783-58390”</strong>, <strong>“Neil Down”</strong>,

<strong>“17 Murray St.”</strong>, <strong>“Nepean”</strong>, <strong>“ON”</strong>));     pdb.<strong>registerDriver</strong>(<strong>new </strong>Driver(<strong>“L5487-16576-38426”</strong>, <strong>“Pete Reedish”</strong>,

<strong>“3445 Bronson Ave.”</strong>, <strong>“Ottawa”</strong>, <strong>“ON”</strong>));

pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Honda”</strong>, <strong>“Civic”</strong>, 2015, <strong>“yellow”</strong>, <strong>“W3EW4T”</strong>),

<strong>“L0453-65433-87655”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Pontiac”</strong>,<strong>“Grand Prix”</strong>,2007,<strong>“dark green”</strong>,<strong>“GO SENS”</strong>),

<strong>“L0453-65433-87655”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Mazda”</strong>, <strong>“RX-8”</strong>, 2004, <strong>“white”</strong>, <strong>“OH YEAH”</strong>),

<strong>“L2333-45645-54354”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Nissan”</strong>,<strong>“Altima”</strong>,2017,<strong>“bergundy”</strong>, <strong>“Y6P9O7”</strong>),

<strong>“L1234-35489-99837”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Saturn”</strong>, <strong>“Vue”</strong>, 2002, <strong>“white”</strong>, <strong>“9R6P2P”</strong>),

<strong>“L2325-45789-35647”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Honda”</strong>, <strong>“Accord”</strong>, 2018, <strong>“gray”</strong>, <strong>“7U3H5E”</strong>),

<strong>“L2325-45789-35647”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Chrysler”</strong>, <strong>“PT-Cruiser”</strong>, 2006, <strong>“gold”</strong>, <strong>“OLDIE”</strong>),             <strong>“L2325-45789-35647”</strong>);

pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Nissan”</strong>, <strong>“Cube”</strong>, 2010, <strong>“white”</strong>, <strong>“5Y6K8V”</strong>),

<strong>“L1948-87265-34782”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Porsche”</strong>, <strong>“959”</strong>, 1989, <strong>“silver”</strong>, <strong>“CATCHME”</strong>),

<strong>“L0678-67825-83940”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Kia”</strong>, <strong>“Soul”</strong>, 2018, <strong>“red”</strong>, <strong>“J8JG2Z”</strong>),

<strong>“L0122-43643-73286”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Porsche”</strong>, <strong>“Cayenne”</strong>, 2014, <strong>“black”</strong>, <strong>“EXPNSV”</strong>),

<strong>“L6987-34532-43334”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Nissan”</strong>, <strong>“Murano”</strong>, 2010, <strong>“silver”</strong>, <strong>“Q2WF6H”</strong>),

<strong>“L3345-32390-23789”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Honda”</strong>, <strong>“Element”</strong>, 2008, <strong>“black”</strong>, <strong>“N7MB5C”</strong>),

<strong>“L3545-45396-88983”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Toyota”</strong>, <strong>“RAV-4”</strong>, 2010, <strong>“green”</strong>, <strong>“R3W5Y7”</strong>),

<strong>“L3545-45396-88983”</strong>);     pdb.<strong>registerVehicle</strong>(<strong>new </strong>Vehicle(<strong>“Toyota”</strong>, <strong>“Celica”</strong>, 2006, <strong>“red”</strong>, <strong>“FUNFUN”</strong>),

<strong>“L5487-16576-38426”</strong>);




<strong>return </strong>pdb;

}




Create the following class as a test program and make sure that it produces the proper output:

<strong>import </strong>java.util.GregorianCalendar;




<strong>public class </strong>PoliceDatabaseTestProgram {     <strong>public static void </strong>main(String args[]) {

PoliceDatabase pdb = PoliceDatabase.<em>example</em>();

System.<strong><em>out</em></strong>.println(<strong>“Here are the drivers:”</strong>);         <strong>for </strong>(<strong>int </strong>i=0; i&lt;pdb.<strong>numDrivers</strong>; i++)

System.<strong><em>out</em></strong>.println(pdb.<strong>drivers</strong>[i]);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the vehicles:”</strong>);         <strong>for </strong>(<strong>int </strong>i=0; i&lt;pdb.<strong>numVehicles</strong>; i++)

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[i]);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Removing 3 vehicles (i.e., W3EW4T, FUNFUN and CATCHME) …”</strong>);         pdb.unregisterVehicle(<strong>“W3EW4T”</strong>);         pdb.unregisterVehicle(<strong>“FUNFUN”</strong>);         pdb.unregisterVehicle(<strong>“CATCHME”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the remaining vehicles:”</strong>);         <strong>for </strong>(<strong>int </strong>i=0; i&lt;pdb.<strong>numVehicles</strong>; i++)

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[i]);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here is the owner of the Honda Accord:”</strong>);

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[4].<strong>owner</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Ilene Dover sells the car to Sam Pull, here is the owner now:”</strong>);         pdb.changeOwner(<strong>“7U3H5E”</strong>, <strong>“L3545-45396-88983”</strong>);

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[4].<strong>owner</strong>);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the stolen cars at this time:”</strong>);         <strong>for </strong>(<strong>int </strong>i=0; i&lt;pdb.<strong>numVehicles</strong>; i++)             <strong>if </strong>(pdb.<strong>vehicles</strong>[i].<strong>reportedStolen</strong>)

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[i]);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Report some cars as stolen…”</strong>);         pdb.reportStolen(<strong>“OH YEAH”</strong>);         pdb.reportStolen(<strong>“OLDIE”</strong>);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the stolen cars now:”</strong>);         <strong>for </strong>(<strong>int </strong>i=0; i&lt;pdb.<strong>numVehicles</strong>; i++)             <strong>if </strong>(pdb.<strong>vehicles</strong>[i].<strong>reportedStolen</strong>)

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[i]);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are some infractions:”</strong>);         Infraction i = <strong>new </strong>Infraction(75, <strong>“Illegal U-Turn”</strong>,                 <strong>new </strong>GregorianCalendar(2017, 11, 14, 7, 8).getTime());         i.pay();

System.<strong><em>out</em></strong>.println(i);

System.<strong><em>out</em></strong>.println(<strong>new </strong>Infraction(175, <strong>“Speeding in excess of 20km”</strong>,                 <strong>new </strong>GregorianCalendar(2018, 1, 2, 14, 22).getTime()));

}

}







Here is the expected output:




Here are the drivers:

#L1567-34323-84980 Matt Adore living at 1323 Kenaston St., Gloucester, ON

#L0453-65433-87655 Bob B. Pins living at 32 Rideau Rd., Greely, ON

#L2333-45645-54354 Stan Dupp living at 1355 Louis Lane, Gloucester, ON

#L1234-35489-99837 Ben Dover living at 2348 Walkley Rd., Ottawa, ON

#L8192-87498-27387 Patty O’Lantern living at 2338 Carling Ave., Nepean, ON

#L2325-45789-35647 Ilene Dover living at 287 Bank St., Ottawa, ON

#L1213-92475-03984 Patty O’Furniture living at 200 St. Laurant Blvd., Ottawa, ON

#L1948-87265-34782 Jen Tull living at 1654 Stonehenge Cres., Ottawa, ON

#L0678-67825-83940 Jim Class living at 98 Oak Blvd., Ottawa, ON

#L0122-43643-73286 Mark Mywords living at 3 Third St., Ottawa, ON

#L6987-34532-43334 Bob Upandown living at 434 Gatineau Way, Hull, QC

#L3345-32390-23789 Carrie Meehome living at 123 Thurston Drive, Kanata, ON

#L3545-45396-88983 Sam Pull living at 22 Colonel By Drive, Ottawa, ON

#L1144-26783-58390 Neil Down living at 17 Murray St., Nepean, ON

#L5487-16576-38426 Pete Reedish living at 3445 Bronson Ave., Ottawa, ON




Here are the vehicles:

A yellow 2015 Honda Civic with plate W3EW4T

A dark green 2007 Pontiac Grand Prix with plate GO SENS

A white 2004 Mazda RX-8 with plate OH YEAH

A bergundy 2017 Nissan Altima with plate Y6P9O7

A white 2002 Saturn Vue with plate 9R6P2P

A gray 2018 Honda Accord with plate 7U3H5E

A gold 2006 Chrysler PT-Cruiser with plate OLDIE

A white 2010 Nissan Cube with plate 5Y6K8V

A silver 1989 Porsche 959 with plate CATCHME

A red 2018 Kia Soul with plate J8JG2Z

A black 2014 Porsche Cayenne with plate EXPNSV

A silver 2010 Nissan Murano with plate Q2WF6H

A black 2008 Honda Element with plate N7MB5C

A green 2010 Toyota RAV-4 with plate R3W5Y7

A red 2006 Toyota Celica with plate FUNFUN




Removing 3 vehicles (i.e., W3EW4T, FUNFUN and CATCHME) …




Here are the remaining vehicles:

A dark green 2007 Pontiac Grand Prix with plate GO SENS

A white 2004 Mazda RX-8 with plate OH YEAH

A bergundy 2017 Nissan Altima with plate Y6P9O7

A white 2002 Saturn Vue with plate 9R6P2P

A gray 2018 Honda Accord with plate 7U3H5E

A gold 2006 Chrysler PT-Cruiser with plate OLDIE

A white 2010 Nissan Cube with plate 5Y6K8V

A red 2018 Kia Soul with plate J8JG2Z

A black 2014 Porsche Cayenne with plate EXPNSV

A silver 2010 Nissan Murano with plate Q2WF6H

A black 2008 Honda Element with plate N7MB5C

A green 2010 Toyota RAV-4 with plate R3W5Y7




Here is the owner of the Honda Accord:

#L2325-45789-35647 Ilene Dover living at 287 Bank St., Ottawa, ON

Ilene Dover sells the car to Sam Pull, here is the owner now:

#L3545-45396-88983 Sam Pull living at 22 Colonel By Drive, Ottawa, ON




Here are the stolen cars at this time:




Report some cars as stolen…

Here are the stolen cars now:

A white 2004 Mazda RX-8 with plate OH YEAH

A gold 2006 Chrysler PT-Cruiser with plate OLDIE




Here are some infractions:

$75.00 Infraction on Thu Dec 14 07:08:00 EST 2017 [PAID IN FULL]

$175.00 Infraction on Fri Feb 02 14:22:00 EST 2018 [OUTSTANDING]










<h1>(4) More on the <strong>PoliceDatabase </strong>Class</h1>

Add the following methods to the <strong>PoliceDatabase</strong> class:

<ul>

 <li><strong>issueInfraction(String license, float amount, String description, Date date)</strong> which causes the driver with the given license to receive an infraction for the given amount and description (i.e., reason) on the given date … updating the database as necessary. This method MUST return the <strong>Infraction </strong>object created. If the number of infractions has reached its limit in the database, then nothing is to be done.</li>

 <li><strong>hasOutstandingInfractions(Driver d) </strong>which returns a <strong>boolean</strong> with a value of <strong>true</strong> if the driver has any infractions that have not been paid yet, otherwise it should return <strong>false</strong>.</li>

 <li><strong>shouldStopVehicle(String plate) </strong>which decides whether or not the police should pull this vehicle over. It should return a <strong>boolean</strong> with a value of <strong>true</strong> if and only if the vehicle has been <strong>reportedStolen</strong>, or if the vehicle’s <strong>owner</strong> has at least one outstanding infraction (you MUST make use of the method <strong><u>hasOutstandingInfractions()</u></strong>).   Otherwise, the method should return <strong>false</strong>.</li>

 <li><strong>showInfractionsFor(String license)</strong> which displays a list of all infractions that the driver with this license ID has incurred showing (on successive lines) the driver’s infractions … and then finish with the total number of outstanding infractions. Here is the format you should use:</li>

</ul>

$100.00 Infraction on Sat Mar 03 11:55:00 EST 1990 [PAID IN FULL]

$250.00 Infraction on Tue Oct 06 09:22:00 EDT 1992 [PAID IN FULL]

$280.00 Infraction on Wed Aug 07 09:05:00 EDT 1996 [PAID IN FULL]

$300.00 Infraction on Fri Mar 03 12:15:00 EST 2000 [OUTSTANDING]

$350.00 Infraction on Mon Feb 01 02:04:00 EST 2010 [OUTSTANDING] Total outstanding infractions = 2

<ul>

 <li><strong>cleanDrivers()</strong> which returns an <strong>Driver[ ]</strong> of all drivers who have never had any infractions. The array should have a length corresponding exactly to the number of clean drivers (i.e., no nulls).</li>

 <li><strong>showInfractionReport()</strong> which lists information about all drivers <u>who have had at least one</u> Each line in the list should show a driver’s name (formatted to take 20 spaces … using the<strong> String.format()</strong>) followed by the number of infractions that they received and the total amount for all infractions that they have <u>already</u> <u>paid</u> (formatted as shown) as follows:</li>

</ul>

Bob B. Pins: 1 infractions, total paid = $ 75.00

Ilene Dover: 4 infractions, total paid = $400.00

Jim Class: 5 infractions, total paid = $630.00

Bob Upandown: 1 infractions, total paid = $  0.00                           … etc…

____________________________________________________________________________________________

<h1>(5) Final Testing</h1>

Define a class called <strong>PoliceDatabaseTestProgram2</strong> as shown on the next page.   Cut and paste the code… do not re-type it.  It would be a good idea to write blank methods for part 4 so that the test code compiles and runs.  Then fill in the methods one at a time and test them.




<strong>import </strong>java.util.GregorianCalendar; <strong>public class </strong>PoliceDatabaseTestProgram2 {

<strong>public static void </strong>addInfractions(PoliceDatabase pdb) {         pdb.issueInfraction(<strong>“L0453-65433-87655”</strong>, 75, <strong>“Illegal U-Turn”</strong>,                 <strong>new </strong>GregorianCalendar(2010, 6, 14, 7, 8).getTime()).pay();         pdb.issueInfraction(<strong>“L2325-45789-35647”</strong>, 175, <strong>“Speeding in excess of 20km”</strong>,                 <strong>new </strong>GregorianCalendar(2011, 2, 2, 14, 22).getTime()).pay();         pdb.issueInfraction(<strong>“L2325-45789-35647”</strong>, 75, <strong>“Illegal U-Turn”</strong>,                 <strong>new </strong>GregorianCalendar(2012, 3, 22, 4, 34).getTime()).pay();         pdb.issueInfraction(<strong>“L2325-45789-35647”</strong>, 150, <strong>“Wrong way up 1-way street”</strong>,                 <strong>new </strong>GregorianCalendar(2014, 6, 14, 8, 2).getTime()).pay();         pdb.issueInfraction(<strong>“L2325-45789-35647”</strong>, 500, <strong>“Running red light”</strong>,                 <strong>new </strong>GregorianCalendar(2017, 9, 12, 5, 15).getTime());         pdb.issueInfraction(<strong>“L0678-67825-83940”</strong>, 100, <strong>“Failure to signal”</strong>,                 <strong>new </strong>GregorianCalendar(2008, 2, 3, 11, 55).getTime()).pay();         pdb.issueInfraction(<strong>“L0678-67825-83940”</strong>, 250, <strong>“Speeding in excess of 30km”</strong>,                 <strong>new </strong>GregorianCalendar(2010, 9, 6, 9, 22).getTime()).pay();         pdb.issueInfraction(<strong>“L0678-67825-83940”</strong>, 280, <strong>“Speeding in excess of 30km”</strong>,                 <strong>new </strong>GregorianCalendar(2015, 7, 7, 9, 5).getTime()).pay();         pdb.issueInfraction(<strong>“L0678-67825-83940”</strong>, 300, <strong>“Speeding in excess of 30km”</strong>,                 <strong>new </strong>GregorianCalendar(2017, 11, 3, 12, 15).getTime());

pdb.issueInfraction(<strong>“L0678-67825-83940”</strong>, 350, <strong>“Speeding in excess of 30km”</strong>,                 <strong>new </strong>GregorianCalendar(2018, 1, 1, 2, 4).getTime());         pdb.issueInfraction(<strong>“L6987-34532-43334”</strong>, 500, <strong>“Running red light”</strong>,                 <strong>new </strong>GregorianCalendar(2017, 7, 2, 22, 17).getTime());         pdb.issueInfraction(<strong>“L3545-45396-88983”</strong>, 75, <strong>“Illegal U-Turn”</strong>,                 <strong>new </strong>GregorianCalendar(2007, 3, 4, 20, 12).getTime()).pay();         pdb.issueInfraction(<strong>“L3545-45396-88983”</strong>, 175, <strong>“Speeding in excess of 20km”</strong>,                 <strong>new </strong>GregorianCalendar(2011, 5, 4, 23, 25).getTime()).pay();         pdb.issueInfraction(<strong>“L1144-26783-58390”</strong>, 175, <strong>“Speeding in excess of 20km”</strong>,                 <strong>new </strong>GregorianCalendar(2012, 10, 1, 19, 38).getTime());         pdb.issueInfraction(<strong>“GARBAGE ID”</strong>, 100, <strong>“Loving Java too much”</strong>,                 <strong>new </strong>GregorianCalendar(2017, 11, 24, 19, 38).getTime());

}

<strong>public static void </strong>main(String args[]) {

<em>// Make a new database and add some vehicles/owners etc..         </em>PoliceDatabase pdb = PoliceDatabase.<em>example</em>();         <em>addInfractions</em>(pdb);




System.<strong><em>out</em></strong>.println(<strong>“Vehicles that should be stopped:”</strong>);         <strong>for </strong>(<strong>int </strong>i=0; i&lt;pdb.<strong>numVehicles</strong>; i++)

<strong>if </strong>(pdb.shouldStopVehicle(pdb.<strong>vehicles</strong>[i].<strong>plate</strong>))

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[i]);

System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Report OH YEAH, W3EW4T and LUVJAVA as stolen:”</strong>);         pdb.reportStolen(<strong>“OH YEAH”</strong>);         pdb.reportStolen(<strong>“W3EW4T”</strong>);

pdb.reportStolen(<strong>“LUVJAVA”</strong>); <em>// This one won’t work, but shouldn’t crash  </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Vehicles that should be stopped:”</strong>);         <strong>for </strong>(<strong>int </strong>i=0; i&lt;pdb.<strong>numVehicles</strong>; i++)

<strong>if </strong>(pdb.shouldStopVehicle(pdb.<strong>vehicles</strong>[i].<strong>plate</strong>))

System.<strong><em>out</em></strong>.println(pdb.<strong>vehicles</strong>[i]);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are all the clean drivers:”</strong>);         <strong>for </strong>(Driver d: pdb.cleanDrivers())

System.<strong><em>out</em></strong>.println(d);




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here is the infraction report:”</strong>);         pdb.showInfractionReport();




System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here is the status of Jim Class:”</strong>);         pdb.showInfractionsFor(<strong>“L0678-67825-83940”</strong>);     }

}

Here is the proper output for the above test case … make sure that it works:

Vehicles that should be stopped:

A white 2002 Saturn Vue with plate 9R6P2P

A gray 2018 Honda Accord with plate 7U3H5E

A gold 2006 Chrysler PT-Cruiser with plate OLDIE

A silver 1989 Porsche 959 with plate CATCHME

A black 2014 Porsche Cayenne with plate EXPNSV




Report OH YEAH, W3EW4T and LUVJAVA as stolen:




Vehicles that should be stopped:

A yellow 2015 Honda Civic with plate W3EW4T

A white 2004 Mazda RX-8 with plate OH YEAH

A white 2002 Saturn Vue with plate 9R6P2P

A gray 2018 Honda Accord with plate 7U3H5E

A gold 2006 Chrysler PT-Cruiser with plate OLDIE

A silver 1989 Porsche 959 with plate CATCHME

A black 2014 Porsche Cayenne with plate EXPNSV




Here are all the clean drivers:

#L1567-34323-84980 Matt Adore living at 1323 Kenaston St., Gloucester, ON

#L2333-45645-54354 Stan Dupp living at 1355 Louis Lane, Gloucester, ON

#L1234-35489-99837 Ben Dover living at 2348 Walkley Rd., Ottawa, ON

#L8192-87498-27387 Patty O’Lantern living at 2338 Carling Ave., Nepean, ON

#L1213-92475-03984 Patty O’Furniture living at 200 St. Laurant Blvd., Ottawa, ON

#L1948-87265-34782 Jen Tull living at 1654 Stonehenge Cres., Ottawa, ON

#L0122-43643-73286 Mark Mywords living at 3 Third St., Ottawa, ON

#L3345-32390-23789 Carrie Meehome living at 123 Thurston Drive, Kanata, ON

#L5487-16576-38426 Pete Reedish living at 3445 Bronson Ave., Ottawa, ON

Here is the infraction report:

Bob B. Pins: 1 infractions, total paid = $ 75.00

Ilene Dover: 4 infractions, total paid = $400.00

Jim Class: 5 infractions, total paid = $630.00

Bob Upandown: 1 infractions, total paid = $  0.00

Sam Pull: 2 infractions, total paid = $250.00            Neil Down: 1 infractions, total paid = $  0.00




Here is the status of Jim Class:

$100.00 Infraction on Mon Mar 03 11:55:00 EST 2008 [PAID IN FULL]

$250.00 Infraction on Wed Oct 06 09:22:00 EDT 2010 [PAID IN FULL]

$280.00 Infraction on Fri Aug 07 09:05:00 EDT 2015 [PAID IN FULL]

$300.00 Infraction on Sun Dec 03 12:15:00 EST 2017 [OUTSTANDING]

$350.00 Infraction on Thu Feb 01 02:04:00 EST 2018 [OUTSTANDING]

Total outstanding infractions = 2


