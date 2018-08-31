## Schedule Session

### Prerequisites for Building
* Java 1.8
* Maven 3(for building)
* JUnit 4(for test dependencies, will be automatically downloaded by Maven)

### Prerequisites for Executing the Program
* Java 1.8

### How to Build

```bash
cd /path/to/project-root
mvn clean package
```

This build task compiles the code, builds a jar file in `target` directory, and executes the
tests.

### How to Run the Program

After `mvn clean package`:

`bash`

	`java -jar target/schedule-sessions-1.0-SNAPSHOT.jar /path/to/input_file`

### Design

#### ConferenceScheduler

* The `ConferenceScheduler` class provides a method called `schedule()` as an API to create a
  `Conference` object representing a scheduled conference with tracks for the provided input
* To schedule the conference, this class currently uses the first-fit algorithm when adding the
  events. In future, we can extend this functionality by accepting a bin-packing algorithm to
  schedule the conference the way the caller of the API wants.

#### Conference

* A `Conference` object currently only returns the schedule as a string via its `toString()`
  method. This also can be easily extended to return the schedule as a list of `Track`s

#### Track

* An object representation of a single track of a conference. Each `Track` object contains one
  or more `Slot`s

#### Slot

* A `Slot` represents a group of events in a `Track` with a fixed start and end time. E.g.: the
  morning slot starting at 9 AM and ending at 12 PM with multiple events in it

#### Event

* An event of the conference

### TODO


* Expand unit tests

